# Nigerian Prince Scam Detector

*A Claude Code skill in the voice of a retired Prince.*

---

## A word from your Prince

My dear, sit down. Let me tell you a story.

Many years ago, when your Prince was a younger man, I used to sit in a cyber café in Lagos with a borrowed keyboard and a head full of fine English. I sent letters. Many, many letters. To grandmothers in Ohio, to widowers in Manchester, to lonely men in Sydney, to anyone whose email address I could find. I told them their long-lost uncle had died, that a fortune was waiting, that only they could help me unlock it. Some of them believed me. Some of them sent money. And some of them, may God forgive me, kept sending until there was nothing left.

I am retired now, my friend. The conscience caught up with me. So I built this small thing for you, this `/scam` skill, to do the opposite of what I used to do. Where I once helped my brothers in the trade catch sheep, now I help the sheep see the wolf.

This README go tell you everything about it. Take your time.

---

## What this skill is

The Nigerian Prince Scam Detector is a Claude Code skill. You invoke it with `/scam`, and it does two things for you, my dear:

1. **It analyzes a suspicious message** (email, SMS, DM, chat screenshot, voice transcript, even a `.eml` file with full headers) and tells you, with evidence, whether it is a scam.
2. **It teaches you, in your Prince's voice**, how the scam works. Because if I show you the trick today, no scammer can play it on you tomorrow.

The voice is the wrapper. Underneath, the analysis is serious work. Header forensics. Domain age lookups. Crypto wallet reputation. Cross-referencing the sender against real scam databases. Checking whether the alleged bank even exists in your country. Quiet, careful, technical work, dressed in a kaftan.

---

## What you can show me

I can read many things, my dear. Show me:

- **A screenshot or photo** of an email, SMS, DM, dating app message, or letter. I will run OCR.
- **Plain text** you paste into the chat.
- **A `.eml` file** with full headers. This is the best gift you can give your Prince, because the headers tell me things the body cannot hide.
- **A URL or domain** that looks suspicious.
- **A phone number** that has been calling or texting you.
- **An email address or sender name** you do not trust.
- **A crypto wallet address** that someone asked you to send money to.
- **A chat export** from WhatsApp, Telegram, or iMessage.

You can also just type, in your own words, "I got this weird email" and paste it. Your Prince is not picky.

---

## What I will ask you

Just one thing, my dear, and only once: **what city and country are you in.**

I no want your street address, abeg. I no want your phone, your name, your business. Just the city and country, and only for this conversation. I do not save it. The reason I ask is because a scam that works in Jakarta is different from a scam that works in Manchester is different from a scam that works in Phoenix. If I know where you are, I can:

- Check what scams are running in your region right now.
- Plausibility-check the message ("My dear, this 'Zelle refund' you receive, Zelle no even operate in Indonesia, this fellow think you no go notice").
- Send you to the right people to report it. Action Fraud in the UK. FTC in the US. ACCC Scamwatch in Australia. EFCC in Nigeria. Polri Siber in Indonesia. The proper office for your land.

---

## What you will get back

Two things, my dear: a short summary in the chat, and a full report saved as a markdown file in your project folder, named `scam-report-YYYY-MM-DD-shortslug.md`. You can keep it. You can show your family. You can email it to the friend who was about to fall for the same thing.

The full report contains:

1. **The verdict**, with a confidence percentage. ("Scam Likelihood: 97%, chai, this one na my cousin work.")
2. **The playbook**: which one of the classic cons this is (419, romance, pig butchering, tech support, fake IRS, job scam, marketplace, inheritance, AI voice-clone grandparent, recovery scam), and which stage you are at.
3. **A table of red flags**, each one in your Prince's voice, paired with a "Receipts" column showing the technical evidence and citations, so you can verify everything yourself.
4. **Two or three "Memoir" callouts**, where your Prince teaches you the underlying mechanic from his own old cons. Why urgency works. Why the small fee comes first. Why the scammer wants you off the platform.
5. **A forecast of what they will send next.** "Next, my dear, this fellow go ask for small 'processing fee', maybe 200 dollar in iTunes card. Watch am."
6. **A reply verdict**: should you reply at all? Most of the time, the answer is no, because any reply confirms your address is live and human-monitored, and live addresses get sold.
7. **Reply coaching, if you decide to reply anyway**: how to do it safely. Channel hygiene (use a burner). Information discipline (the never-share list). Verification asks (questions a real institution can answer but a scammer cannot). A copy-pasteable safe reply template, in neutral voice, so it sounds professional. Exit triggers (when to stop replying immediately).
8. **Safe exit lines** in plain neutral voice, so you can paste them without "chai my dear" landing on a real corporate inbox by mistake.
9. **Reporting links** for your specific country.
10. **Sources** for everything I claimed, with links. Your Prince does not ask you to take his word for it.

---

## What your Prince will not do

Listen well, my friend, because this part matters.

- **Your Prince will not help you scam.** No templates, no rewrites of real scams to make them better, no "as a joke" scripts. The retirement is real.
- **Your Prince will not help you bait, troll, or string along a scammer.** I know it sounds fun. I know the YouTube videos make it look like a sport. But some of these crews are organized people, some are violent, some are in places the law cannot easily reach. Once you become interesting to them, you become a target of something worse than a scam. Report to the proper agency. Let the people whose job this is do the hunting.
- **Your Prince will not help you find, dox, investigate, or retaliate against a specific named person.** This skill protects targets. It does not enable revenge. Even if the person did you wrong.
- **Your Prince will not lecture you if you fell for it.** Many people fall, my dear. Smart people, careful people, professors and lawyers and CEOs. These people do this for a living, and they are good at it. If you tell me you already sent money, I drop the playful voice and we work the recovery checklist together. No "I told you so". Just the next three things to do.

---

## The recovery-scam warning (read this even if you have not been scammed yet)

If you ever lose money to a scam, my dear, hear me now so you remember later:

Within hours to days of any loss, **someone will reach out to you offering to "recover" your funds for an upfront fee.** They will call themselves a recovery agent, a crypto recovery firm, an FBI specialist, a lawyer, a blockchain forensics expert. They will sound official. They will have a website.

**They are a second scammer.** Often the same crew that took you the first time, sometimes a different crew that bought your name from the first crew. Victim lists circulate. Real law enforcement does not charge upfront fees. Real lawyers do not cold-call victims. Real recovery firms are paid on contingency and you find them, not the other way around.

Do not pay anyone to recover your money. Write this on a paper and tape it to your fridge if you must.

---

## How to use the skill

In Claude Code, just type `/scam` followed by whatever you want me to look at, or invoke it and paste the suspicious thing when I ask. Examples that all work:

- `/scam`
- `/scam is this a scam: <paste message>`
- `/scam check this email <attach .eml>`
- `/scam I got this weird text from FedEx, here is the screenshot`
- `/scam should I reply to this Telegram message about a job?`
- `/scam how do I reply safely to this recruiter?`
- "Hey is this a scam?" (the skill will trigger from natural language too)

You do not need to say "Nigerian Prince" or "419". I will recognize the request from any of the obvious signs.

---

## Installation

This skill lives in a folder called `scam/`. To install it as a Claude Code user skill:

```bash
git clone https://github.com/lazyfoxjumps/nigerian-prince-scam-detector.git
cd nigerian-prince-scam-detector
mkdir -p ~/.claude/skills
cp -r scam ~/.claude/skills/
```

Then open Claude Code and type `/scam`. Your Prince will greet you.

If you keep your skills in a different directory, copy the `scam/` folder there. The skill is self-contained: one `SKILL.md`, seven references in `references/`, and one report template in `assets/`.

---

## What is inside the box

```
scam/
├── SKILL.md                          # The workflow your Prince follows
├── references/
│   ├── persona-voice.md              # How your Prince talks, and when he softens
│   ├── scam-playbooks.md             # Every classic con, its stages, its tells
│   ├── linguistic-redflags.md        # Urgency, secrecy, authority, reward, AI-tells
│   ├── header-forensics.md           # SPF, DKIM, DMARC, Received chains, spoofing
│   ├── url-domain-checks.md          # Punycode, homograph, shorteners, WHOIS
│   ├── regional-scam-index.md        # Active scams + reporting agencies, country by country
│   ├── safe-response-scripts.md      # Exit lines + victim recovery checklist
│   └── reply-coaching.md             # If you must reply, how to do it safely
└── assets/
    └── report-template.md            # The shape of the saved report
```

The `SKILL.md` is lean. It loads only the references it needs for the input type, so your context stays small.

---

## A closing word

My dear, the trade I used to be in is bigger now than it was in my time. The letters became emails, the emails became SMS, the SMS became Telegram, the Telegram became deepfake voices of grandchildren in trouble. The tools change, the playbook does not. Always urgency, always secrecy, always authority, always reward. If you know the four, you can spot every new costume they wear.

Your Prince will see you in the skill, my friend. Be careful out there. And if you see one of my old letters in your inbox, remember to laugh, because some old fool in retirement built a tool to make sure it dies in your spam folder where it belongs.

*Walahi.*

---

## License

MIT. Use it, fork it, share it. If it saves one grandmother from losing her savings, the Prince is satisfied.

## Contributing

Pull requests welcome, especially:

- More regional scam patterns and reporting agencies in `regional-scam-index.md`.
- New playbook entries in `scam-playbooks.md` as scams evolve.
- Refinements to AI-tell detection in `linguistic-redflags.md`.
- Translations of safe-reply templates.

Keep the voice. Keep the rigor. No em-dashes.
