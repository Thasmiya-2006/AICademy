# AI-Cademy: From Learning to Measurable Capability

## About the project
AI-Cademy is a frontend prototype of a capability engineering platform that closes the gap between completing courses and being ready for a job. Inspired by the idea of a "Digital Twin of Student Capability", it shows how a platform could discover a student's best-fit career direction, guide them through daily-practice training tracks, and turn their progress into measurable proof of job readiness.

**Sections (tabs):**
- **Home:** Digital Twin profile card, Job Readiness Score, and the problem/solution overview.
- **Direction Discovery:** interest assessment and a sample role recommendation.
- **Capability Tracks:** four training tracks with daily practice, tests and projects.
- **Readiness Dashboard:** job-ready score ring, execution logs and proof artifacts.
- **AI Tutor:** a chat-style demo. The suggested-question chips are labels for hidden radio buttons, so clicking one swaps in a predefined tutor answer using CSS only. Responses are samples, not live AI.

**Status:** static UI/UX prototype for a hackathon demo. All scores, logs and links are sample data.

**Pitch:** AI-Cademy replaces fragmented educational tools with one continuous system that tracks real ability, guides professional preparation, and engineers job readiness.

Built with **HTML, CSS and Bootstrap 5 only**. There is no JavaScript.

## Files
- `index.html`: markup and the hidden radio buttons that control the tabs
- `style.css`: all custom styling and the tab show/hide logic
- `logo.png`, `logo-icon.png`, `favicon.png`: transparent versions made from the supplied logo (full lockup, icon only, browser-tab icon)

## How the CSS-only tabs work (radio button hack)
1. Four hidden `<input type="radio" name="tab">` elements sit at the top of `<body>`, before the header and `<main>`. Only one radio in a group can be checked at a time.
2. Each nav item is a `<label for="tab-...">`. Clicking a label checks the matching radio, so no script is needed.
3. Every section has the class `.panel`, which is `display: none` by default.
4. A sibling selector shows the panel for the checked radio:
   ```css
   #tab-tracks:checked ~ main #tracks { display: block; animation: fadeIn .5s ease both; }
   ```
   This only works because the radios come *before* `main` in the HTML. Keep that order.
5. The same pattern highlights the active nav label. `display` can't be transitioned, so the fade-in is a CSS `animation` using opacity.
6. Buttons such as "Start Discovery" are labels pointing at a radio, so they switch tabs too.
7. The mobile hamburger uses a hidden checkbox and `:checked ~ .nav-links` (the "checkbox hack"). Tap the hamburger again to close the menu.
8. The interest pills on the Discovery tab are hidden checkboxes styled with `:checked + label`.

## Run and deploy
Open `index.html` in a browser (internet needed for the CDN assets). For Netlify, drag the folder onto https://app.netlify.com/drop. No build command is required.

## Notes
All scores, logs and links are sample data for the demo. The AI Tutor is a static UI demonstration with predefined answers.

© 2026 AI-Cademy. All rights reserved.
