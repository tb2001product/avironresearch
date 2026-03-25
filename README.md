# Aviron Survey Intel — Internal Chatbot

An internal AI-powered chatbot for querying the **Aviron Product Survey (February 2026)**. Ask questions in plain English and get instant, data-backed answers from 730 customer responses.

> 🔒 **Internal use only.** Password protected.

---

## What It Does

This tool lets any Aviron team member ask natural language questions about the Feb 2026 product survey — no data skills required. The full survey dataset is embedded directly in the app and powered by Claude (Anthropic).

**Example questions you can ask:**
- *"What are the top complaints from unhappy users?"*
- *"Who is our typical customer demographically?"*
- *"What's the #1 magic wand feature request from rower owners?"*
- *"Why are non-members not paying for a membership?"*
- *"How do treadmill users differ from rower users in content satisfaction?"*
- *"What % of users are aware we release new content every month?"*

---

## Survey Coverage

| # | Questions Covered |
|---|---|
| Q1–Q6 | Demographics (age, gender, income, marital status, parent status) |
| Q7–Q9 | Purchase drivers, NPS/recommendation, weight loss outcomes |
| Q10–Q13 | Brand perception, science-backed, tagline resonance |
| Q14 | GLP-1 sentiment |
| Q15–Q18 | Products owned, usage duration & frequency, membership status |
| Q19 | Non-membership reasons (n=107) |
| Q20–Q21 | 2025 updates rating + open feedback (n=57, conditional) |
| Q22–Q26 | Fitness goals, progress, challenges, motivators |
| Q27–Q29 | Progress tracking apps, sharing behaviour |
| Q30–Q36 | Workout discovery, content awareness & quality |
| Q37–Q39 | Top improvement areas, open-ended change requests, magic wand features |
| Q40 | Follow-up interview interest |

**730 total responses · Exported March 25, 2026**

---

## Accessing the Tool

1. Open the hosted URL (see your team Notion page or ask your manager)
2. Enter the team password when prompted
3. Start asking questions

The chatbot remembers context within a session — you can ask follow-up questions naturally.

---

## Hosting

The chatbot is a **single self-contained HTML file** (`index.html`) hosted on GitHub Pages.

**Live URL:**
```
https://avironactive.github.io/survey-chatbot
```
*(replace with your actual Pages URL once enabled)*

---

## Updating the Tool

If the survey data or chatbot needs to be updated:

1. Clone this repo
2. Edit `index.html` — the survey data is embedded as JSON in a `<script type="application/json">` tag near the top of the file
3. Commit and push to `main` — GitHub Pages will redeploy automatically within ~60 seconds

To update the **password**, search for `const PASSWORD =` in `index.html` and change the value.

To update the **API key**, search for `const API_KEY =` in `index.html` and replace it.

---

## Tech Stack

| Component | Details |
|---|---|
| Frontend | Vanilla HTML/CSS/JS — zero dependencies, no build step |
| AI Model | Claude Sonnet (Anthropic API) |
| Data | Aviron Feb 2026 survey — 730 responses, 40 questions |
| Hosting | GitHub Pages |
| Auth | Client-side password gate (session-based) |

---

## Cost

Each conversation uses the Anthropic API. Estimated cost per session: **~$0.02–0.05** depending on question length and depth. The API key is shared across the team — monitor usage at [console.anthropic.com](https://console.anthropic.com).

---

## Security Notes

- The password gate prevents casual access but is **not enterprise-grade security** — the source code (including the API key) is visible to anyone who views page source
- Do not share the GitHub repo URL publicly — share only the GitHub Pages URL
- If the API key is ever compromised, generate a new one at [console.anthropic.com](https://console.anthropic.com) and update `index.html`
- Survey data does not include any PII beyond email addresses collected for the gift card draw — emails are present in the raw data but not surfaced by the chatbot

---

## Questions / Issues

Contact the marketing or product team. For API issues, check [status.anthropic.com](https://status.anthropic.com).
