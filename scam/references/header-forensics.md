# Email Header Forensics

Use when the user supplies a forwarded `.eml` file or full headers. Read headers separately from body; the body lies, the headers lie less.

## What to extract

From the raw `.eml`, pull these headers in order:

1. `From:` (display name + address)
2. `Reply-To:`
3. `Return-Path:` (envelope sender)
4. `To:` and `Cc:`
5. `Subject:`
6. `Date:`
7. `Message-ID:`
8. `Authentication-Results:` (the receiving server's verdict on SPF, DKIM, DMARC)
9. All `Received:` headers (read bottom-up, that is the chronological path)
10. `X-*` headers (often reveal mail server software, originating IPs, spam scores)

## The four core checks

### Check 1: SPF (Sender Policy Framework)

In `Authentication-Results`, find `spf=`. Values:

- `pass`: sending server is authorized for the From domain. Good.
- `fail`: server is NOT authorized. Strong forgery signal.
- `softfail`: probably not authorized.
- `neutral` / `none`: domain has no SPF policy. Common, not a verdict on its own.
- `temperror` / `permerror`: lookup failed. Inconclusive.

### Check 2: DKIM (DomainKeys Identified Mail)

In `Authentication-Results`, find `dkim=`. Values:

- `pass`: message was cryptographically signed by the claimed domain. Good.
- `fail`: signature broken or forged.
- `none`: no DKIM signature. Common for small senders, suspicious for large institutions (banks, big tech).

### Check 3: DMARC

`dmarc=pass` means SPF or DKIM aligned with the From domain. Big institutions (banks, PayPal, Microsoft, Google, Apple, government) should always pass DMARC. A DMARC fail on a message claiming to be from such an institution is a near-certain forgery.

### Check 4: Display-name spoofing and address mismatch

Compare:

- `From:` display name vs. `From:` actual address. "PayPal Support <paypal-billing@gmail.com>" is spoofing.
- `From:` address vs. `Reply-To:` address. If they differ, the scammer wants replies to go elsewhere.
- `From:` address vs. `Return-Path:`. Mismatch suggests envelope forgery.
- The `From:` domain itself: is it the real domain, or a lookalike (`paypa1.com`, `secure-paypal.net`, `paypal.support-billing.com`)?

## Received chain sanity

Each `Received:` header is added by a mail server in the path. Read bottom to top.

Look for:

- **Originating IP** in the bottom-most `Received:` header. Geolocate it (WebSearch the IP). A "Bank of America" email originating from a residential IP in a country with no BoA operations is a tell.
- **Hop consistency**: real corporate mail flows through known infrastructure (e.g., Google Workspace, Microsoft 365, Mailgun, SendGrid, the company's own MX). A "PayPal" email that never touches PayPal's mail infrastructure is a tell.
- **Timestamp gaps**: huge delays between hops can indicate spoofed headers.
- **Suspect helo names**: `helo=localhost`, `helo=user-pc`, `helo=workgroup` from a "corporate" sender.

## Common forgery patterns

1. **Display-name only spoof**: From line shows "Amazon" but the address is a random Gmail. SPF / DKIM checks on the actual address often pass (because Gmail is real), but the message is still a scam.
2. **Lookalike domain**: `amaz0n-support.com`, `amazon-securityalert.com`. SPF / DKIM may pass for the lookalike domain, but the domain itself is new and unrelated.
3. **Compromised real account**: a real legitimate account, hijacked. Headers all check out. Tell: voice, request, and context do not match prior conversations or the account owner's profile.
4. **Direct header forgery**: From line forged. SPF / DKIM / DMARC fail on big domains. Easy catch.

## What to report

For each .eml analysis, the Receipts column should include:

- SPF, DKIM, DMARC verdicts (verbatim from Authentication-Results).
- From address vs. Reply-To address (note any mismatch).
- Originating IP and rough geolocation.
- Domain age of the From domain (link to WHOIS lookup).
- Any lookalike detection (visual diff of the From domain vs. the impersonated brand).

If SPF/DKIM/DMARC all pass and the domain is the real one and the originating IP is consistent, this is probably NOT a header-level forgery. The scam, if any, is in the content or a compromised account, not in the envelope.
