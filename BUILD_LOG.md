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

## Design reference research (2026-09-21, follow-up request)

You asked me to find a standout portfolio site and rebuild the background/layout to match it, without touching any content. Since a written description isn't proof of what a site actually looks like, I pulled real rendered screenshots (via each site's own og:image where useful, and via a screenshot proxy for the live page) rather than relying on my own memory or on WebFetch's HTML-to-markdown conversion, which strips CSS and can only guess at visuals.

**What I looked at:**
- **Brittany Chiang** (brittanychiang.com) — confirmed via screenshot: navy background, sticky left sidebar (name/nav) + scrolling right content, mint accent. Ruled out as the reference: it's become the most-cloned developer portfolio layout in the industry, i.e. close to the definition of "generic dev portfolio" you were trying to avoid.
- **Cassie Evans** (cassie.codes) — a design roundup described an illustrated-desk-scene layout, but a live screenshot showed she's taken the site down (a farewell note, dated). Dropped since the described design no longer exists.
- **Rauno Freiberg** (rauno.me) — confirmed via screenshot. Off-white page background, a white content panel that sits proud of the page, oversized bold black display type stacked tightly, one large flat solid-color circle overlapping the type as a compositional anchor, and tiny monospace micro-marks (a small ruler/tick icon) instead of gradients or glassmorphism. Genuinely distinctive, and achievable in plain CSS.

**What I picked and why:** Rauno Freiberg's site, for its layout language — oversized type, one flat color-block shape as an anchor, panel-on-page contrast, monospace micro-details — rather than its literal light color scheme. You asked to keep the site dark, so I translated the same composition principles onto the existing dark palette instead of copying the light background directly.

**What I changed (style/layout only — verified zero text-node or href differences via a diff against a pre-edit content extraction):**
- Removed the graph-paper grid background image and the glassy/blurred sticky topbar — replaced with a flat, solid dark background (no gradients, no glassmorphism).
- Rebuilt the hero into a bordered panel (echoing rauno's white card floating on a grey page) containing much larger, tighter-set display type for the name, with a large flat solid green circle overlapping the corner as the compositional anchor, plus a small decorative monospace tick/ruler mark — all new wrapper `<div>`s, no existing text touched.
- Added large "ghost" numerals behind each section header (00–05), reusing the exact digits already visible in each section's small index label, rendered huge and low-contrast via a CSS `::before` on the section, purely decorative.
- Flattened the career-timeline SVG: removed the animated dots traveling along the connector lines (a very common "AI-template roadmap" flourish), sharpened the node corners, and made the current role (Mercor) a solid flat green block instead of a dashed-amber outline — same six milestones, same text, same links.
- Flattened cards, status tags, skill tags, and the awards log panel: smaller border radii, a left accent bar instead of a full glowing border/box-shadow on hover, no rounded pill glassiness.
- Fixed a real (if minor) responsive bug I found while testing this: the topbar's six nav links had no wrap behavior and would have overflowed on narrow phones. Added `flex-wrap` at both the topbar and nav level so links reflow to additional rows instead of getting clipped.

**What I wasn't able to fully verify:** this session's headless-Chrome testing setup has a hard floor of ~500px for the simulated viewport width, so I could not get a true screenshot below that (screenshots requested at 390px actually rendered internally at 500px and then got cropped to 390px, which looked like overflow but wasn't). I confirmed the fix analytically instead — CSS `flex-wrap` mathematically cannot overflow its container, it reflows to new lines — and confirmed everything renders cleanly at the narrowest width I could reliably test (500px). Worth a real-device or real-browser check on an actual phone after this goes live.

