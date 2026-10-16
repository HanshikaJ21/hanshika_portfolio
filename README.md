# Hanshika Jasuja: Portfolio

A single-file static site (HTML + CSS + JS, no build step).

## Files
- `index.html`: the whole site (images are embedded, so nothing else is needed to run it)
- `Hanshika_Jasuja_Resume.pdf`: served by the Resume buttons

## Run locally
Open `index.html` in a browser, or run `npx serve .` in this folder.

## Deploy (free)
- **Vercel:** drag this folder onto vercel.com/new, or run `npx vercel` here.
- **Netlify:** drag the folder onto app.netlify.com/drop.

## Edit content
Open `index.html` and search for `const D=`. Projects (`D.p`), experience (`D.x`) and skills (`D.s`) all live there.
- Add a real project screenshot: give that project an `s:'images/name.png'` field and put the file in an `images/` folder. It replaces the drawn preview.
- Result badges come from each item's `m:[...]` list.
- Replace the PDF with a new resume of the same file name to update the download.
- The Projects section fetches the four most recently updated public GitHub repositories on page load. Matching featured projects keep their hand-written details; new repositories use their GitHub description, language, topics and homepage. Forks and portfolio repositories are excluded. This live sync requires the visitor's browser to reach the public GitHub API; private repositories are not exposed.

## Notes
- The chat assistant answers from your resume data. Free-form AI answers only work inside claude.ai; elsewhere it falls back to resume-based answers. For real AI chat on your own domain, add a small serverless function that calls the Claude API (keep the API key server-side, never in the page).
- Dark mode toggle remembers the visitor's choice. Animations respect "reduce motion".
