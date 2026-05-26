# URL and Domain Checks

For any URL or domain in the suspicious message, run these checks. Do not click the link in the user's browser; do not have the user click it. Use WebFetch to inspect content if needed, with care.

## 1. Shortener expansion

If the URL uses a shortener (`bit.ly`, `tinyurl.com`, `t.co`, `goo.gl`, `is.gd`, `ow.ly`, `cutt.ly`, `rebrand.ly`, custom-branded shorteners), expand it before analyzing.

- WebFetch the shortener URL and follow redirects.
- If you cannot expand safely, search for the shortener path on URL-expansion services or note in the report that the destination is unknown and treat as hostile.

## 2. Punycode and homograph attacks

A domain that looks like `apple.com` may actually be `аpple.com` (with a Cyrillic а). Check for:

- **Punycode**: domains starting with `xn--` are Unicode encoded. Decode to see the real characters.
- **Homograph swaps**: common substitutions:
  - `0` for `o` (`paypa0.com`)
  - `1` for `l` (`paypa1.com`)
  - `rn` for `m` (`arnazon.com`)
  - Cyrillic `а`, `е`, `о`, `р`, `с`, `х` for Latin a, e, o, p, c, x
  - Greek `ο` for o
  - Extra hyphens (`pay-pal-secure.com`)
- **Subdomain trickery**: `paypal.com.secure-login.xyz`. The real domain is the rightmost, before the TLD. Here it is `secure-login.xyz`, not paypal.

## 3. WHOIS domain age

WebSearch `whois <domain>` or use `https://who.is/whois/<domain>`.

Domains under 90 days old, for any message claiming to be from an established institution, are a strong red flag. Scam infrastructure is disposable and constantly rebuilt.

Note the creation date, registrar, and registrant country (often privacy-masked, which itself for a "bank" is suspicious).

## 4. Safe Browsing and reputation

Check the URL against:

- Google Safe Browsing (`https://transparencyreport.google.com/safe-browsing/search`).
- PhishTank (`https://phishtank.org`).
- URLhaus (`https://urlhaus.abuse.ch`).
- VirusTotal (`https://www.virustotal.com/gui/home/url`).
- ScamAdviser (`https://www.scamadviser.com`).

A clean Safe Browsing record does NOT mean a domain is safe; new phishing domains often fly under the radar for hours to days. A flagged record is conclusive.

## 5. SSL certificate sanity

When you WebFetch the domain (carefully), note:

- Does the cert match the domain? Let's Encrypt certs are cheap and free; their presence is not validation, but a cert mismatch warning is a strong tell.
- Wildcard certs and very recently issued certs on a "bank" domain are suspicious.

## 6. Content sniff (with caution)

If you WebFetch the destination, look for:

- A login form that posts to a different domain.
- Branding pulled from the real institution (logos, copyright text) but a different domain in the URL bar.
- Iframes pointing to the real institution (to look legit) wrapped around a fake form.
- Surveys or "verify your identity" prompts that ask for SSN, full card number + CVV, OTP codes, or password.

Never have the user paste credentials into a fetched page.

## 7. Brand impersonation cross-check

If the domain claims to be a brand, WebSearch the brand's real verified domain. Most large brands publish their official domains on a "report phishing" page (e.g., Microsoft, PayPal, Apple, IRS, USPS). Compare side by side.

## What to report

For each URL or domain analyzed, the Receipts column should include:

- Expanded final URL (if shortened).
- Punycode / homograph notes if any.
- Domain age and registrar.
- Safe Browsing / PhishTank / URLhaus verdicts.
- A link to the WHOIS record and to the safe-browsing search result so the user can verify.
