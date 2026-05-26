# Changelog

All notable changes to the Nigerian Prince Scam Detector skill will be documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). Versions follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2026-05-24

The Prince comes out of retirement. First public release.

### Added
- `scam/SKILL.md`: main workflow, intake (city + country, session-scoped), parallel analysis engine, three voice modes (Full Prince, Softened Prince, Hard Refusal), save-as-markdown report pipeline.
- `scam/references/persona-voice.md`: West African English voice rules, victim-trigger detection, professor-mode formatting, three-mode decision logic.
- `scam/references/scam-playbooks.md`: 9 playbooks (419 / advance-fee, romance / pig butchering, tech support, fake authority, job and recruiter, marketplace overpayment, inheritance / lottery / parcel, AI voice-clone grandparent, recovery scams) with stages, telltale phrases, and "next message" forecasts. Stage labeling system (Stage 0 to Stage 5).
- `scam/references/linguistic-redflags.md`: 5-axis scoring system (urgency, secrecy, authority, reward, grammar / AI tells) with bonus signals and a 0 to 12+ verdict scale.
- `scam/references/header-forensics.md`: SPF / DKIM / DMARC interpretation, Received chain reading, display-name spoofing, lookalike domains, common forgery patterns.
- `scam/references/url-domain-checks.md`: shortener expansion, punycode and homograph detection, WHOIS domain-age lookup, Safe Browsing / PhishTank / URLhaus / VirusTotal / ScamAdviser cross-checks, SSL sanity, brand impersonation comparison.
- `scam/references/regional-scam-index.md`: per-country active scam patterns and reporting agencies for US, UK, AU, CA, EU (DE / FR / NL / ES), Nigeria, Indonesia, India, Philippines, Singapore, plus a generic fallback workflow.
- `scam/references/safe-response-scripts.md`: neutral-voice exit lines by scam type, victim recovery checklist (minutes / hours / days timeline), mandatory recovery-scam warning, emotional support guidance.
- `scam/references/reply-coaching.md`: reply verdict logic (DO NOT REPLY / SAFE TO REPLY / REPLY ONLY IF YOU MUST), channel hygiene, never-share list, verification asks scripted per scam type, copy-pasteable safe-reply templates, exit triggers, hard refusal for scam-baiting.
- `scam/assets/report-template.md`: 10-section saved report structure with reply verdict, coaching block, and citations.
- `README.md`: full scope of the skill written entirely in the Prince's voice.
- `LICENSE`: MIT.
- `.gitignore`: excludes saved `scam-report-*.md` files from version control.
- GitHub repo topic tags: `claude-code`, `claude-skill`, `scam-detection`, `phishing-detection`, `anti-scam`, `anti-phishing`, `419-scam`, `romance-scam`, `pig-butchering`, `email-security`, `fraud-detection`, `nigerian-prince`, `ai-agent`, `security-tools`, `osint`.

### Voice and safety guardrails
- Three voice modes with explicit trigger conditions (default, victim, refusal).
- Never generates usable scam content (no templates, no rewrites).
- Refuses scam-baiting, doxxing, retaliation requests.
- Mandatory recovery-scam warning in all victim-mode reports.
- City-level location only; session-scoped; never persisted.
- All output forbids em-dashes and en-dashes.

---

## Roadmap (planned, not yet released)

### [1.1.0] - planned
- Expand `regional-scam-index.md` with Latin America (BR, MX, AR), Middle East (AE, SA, IL), and additional Africa (KE, ZA, GH) entries.
- Add Mandarin / Cantonese pig butchering pattern detection (the original "sha zhu pan" playbook in source language).
- Worked-example sample report in the README.

### [1.2.0] - planned
- Optional `transcript-mode` for analyzing voice-call transcripts (AI voice-clone grandparent, vishing).
- Image-EXIF check for sender profile photos (detect stock-photo metadata).

### [2.0.0] - planned
- Multi-message thread analysis (paste an entire conversation; the Prince scores the escalation pattern across messages).
- Optional telemetry-free local database of scammer wallets / emails / phones, contributed by users via PR.

---

*The Prince logs his work. Walahi.*
