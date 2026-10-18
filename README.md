# Hanshika Jasuja: Portfolio

A mostly single-file portfolio (HTML + CSS + JS, no build step) with a Vercel serverless chat API.

## Files
- `index.html`: the site markup, styles and scripts
- `images/live-work/`: optimized screenshots used as live-work card previews
- `api/chat.js`: Vercel serverless function for the AI chat
- `Hanshika_Jasuja_Resume.pdf`: served by the Resume buttons

## Run locally
Run `npx vercel env pull .env.local` and then `npx vercel dev` to test the chat API locally. Opening `index.html` directly or using a static-only server still displays the portfolio, but the AI chat needs the API function.

## Deploy (free)
- **Vercel:** drag this folder onto vercel.com/new, or run `npx vercel` here.
- **Netlify:** drag the folder onto app.netlify.com/drop. This static deployment will not run the Vercel chat function, so AI chat requires a separate function adapted for Netlify.

## Edit content
Open `index.html` and search for `const D=`. Projects (`D.p`), experience (`D.x`) and skills (`D.s`) all live there.
- The selected live websites and contact email are in the relevant sections of `index.html`.
- Add a real project screenshot: give that project an `s:'images/name.png'` field and put the file in an `images/` folder. It replaces the drawn preview.
- Result badges come from each item's `m:[...]` list.
- Replace the PDF with a new resume of the same file name to update the download.
- The Projects section fetches the four most recently updated public GitHub repositories on page load. Matching featured projects keep their hand-written details; new repositories use their GitHub description, language, topics and homepage. Forks and portfolio repositories are excluded. This live sync requires the visitor's browser to reach the public GitHub API; private repositories are not exposed.

## Notes
- The chat assistant uses the Gemini 3.5 Flash-Lite API through `api/chat.js` to answer general questions and questions about the resume. To enable it on Vercel, create a Gemini API key in [Google AI Studio](https://aistudio.google.com/apikey), then add it as `GEMINI_API_KEY` under the Vercel project's **Settings → Environment Variables** and redeploy. Keep billing disabled to stay on Google's free tier; free-tier limits apply, and Google says free-tier content may be used to improve its products. The key must never be added to `index.html` or committed to the repository.
- The chat API validates message sizes and keeps only the last three turns. If the API is unconfigured, unavailable, or opened outside Vercel, resume-related questions use the built-in answers and other questions show an unavailable message.
- Dark mode toggle remembers the visitor's choice. Animations respect "reduce motion".
