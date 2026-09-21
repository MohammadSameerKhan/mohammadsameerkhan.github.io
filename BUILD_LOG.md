# Build log — one-page portfolio (2026-09-21)

## What I looked at
- `Mohammad_Sameer_Khan_Resume.pdf` (full text extracted) — used as the primary source for summary, skills, experience, projects, education, and leadership dates/facts.
- The `index.html` already committed in this repo (from a prior "Add files via upload" commit) — a dark, techy single-page design with sections for About, Experience, Projects, Leadership, Education, Awards, and Contact.
- Checked this session's scratchpad, `~/Downloads`, and `~/Desktop` for LinkedIn screenshots — none were found or attached in the conversation.

## What I decided
- You confirmed you wanted me to treat the content already in `index.html` as the reference material (standing in for the LinkedIn screenshots, which weren't actually attached), and to keep the Awards/Certifications section as-is.
- Given that, I used the resume as the authoritative source for anything the resume covers, and corrected the following mismatches against it:
  - Mercor bullets replaced with the resume's actual 3 bullets (the prior text was more generic/embellished and didn't match).
  - Handshake bullets replaced with the resume's actual 2 bullets (prior version had 5 embellished bullets not in the resume).
  - MaxwellStamp: fixed company name from "Maxwell Stamp Limited" → "MaxwellStamp LLC" and title from "Software Developer" → "Software Developer Intern" (both per resume), and swapped bullets for the resume's 2 actual bullets.
  - Best Buy bullets already matched the resume verbatim — left unchanged.
  - Removed the "Open-source repos" project card entirely. It wasn't listed on the resume, and your first instruction was explicit: only include projects that are actually on the resume, nothing pulled from GitHub. This also removed an unverifiable claim about catching a live OAuth secret leak.
  - Kept Projects section to exactly the two resume-listed projects: GhostByte and AI_Khan_BOT.
  - Added your phone number to the Contact panel (it's on the resume but wasn't in the existing contact list).
  - Lightly rewrote the About paragraph to track the resume's summary more closely (including the "Best Senator" recognition line, which is directly in the resume).
- Left untouched, per your direction to keep them as trusted reference content (none of this is in the resume, so I could not independently verify it):
  - The **Front Desk Attendant** role (St. Cloud State, Sep 2022–May 2023) — not on the resume.
  - The entire **Awards & Certifications** section (Senator of the Year, Pakistan Student Association President Award, Certificate of Appreciation, Elections Chair Award, various SCSU badges, a "micro1"-issued cert).
  - Extra technical specifics in the Projects section beyond what the resume states: GhostByte's Edge TTS / Pexels / FFmpeg / `NODE_FUNCTION_ALLOW_BUILTIN=crypto` debugging detail and the live YouTube channel link; AI_Khan_BOT's Binance.US API and the specific pairs BTCUSDT/ETHUSDT/SOLUSDT/XRPUSDT (the resume only says "four cryptocurrency pairs," doesn't name an exchange).
  - The Skills section's extra tags beyond the resume's literal skill list (e.g., "REST APIs," "Data Pipelines," n8n/webhooks/ngrok infra tags, "Search Relevance Assessment," IT/leadership tags) — plausible given the experience described, but not verbatim resume items.

## What I wasn't sure about
- I still can't independently verify the Front Desk Attendant job or the Awards/Certifications entries against a resume or LinkedIn — they exist only because the repo's prior `index.html` had them and you told me to trust that content in place of the (never-attached) LinkedIn screenshots. If any of those are inaccurate or outdated, let me know and I'll pull them or fix them.
- Same caveat for the extra project implementation details noted above (Edge TTS, Pexels, Binance.US, specific coin pairs, etc.) — these go beyond what's stated in the resume.
- I could not do a live visual QA pass in a browser (the Claude-in-Chrome extension wasn't connected this session). I did validate the HTML structurally (balanced tags, no syntax breakage) and served it locally, but you should give it a look in an actual browser after it's live.
- I didn't check/enable GitHub Pages settings via the API (no `gh` CLI in this environment). Since this is a `<username>.github.io` repo, Pages is usually already serving from `main` — worth a quick check under Settings → Pages after this push if the site doesn't update.
