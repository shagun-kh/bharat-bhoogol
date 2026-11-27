# Bharat Bhoogol · भारत भूगोल

An interactive quiz on India's political map from 1950 to today. Pick any date, see India's states and union territories as they were on that day, then drag states into place, pin their capitals and share quizzes with friends.

Built for UPSC and competitive-exam geography practice, and for anyone curious about how India's map has changed.

## Features

- **The map on any date:** the time slider runs from 26 January 1950, when the Constitution came into force, to today. It covers 32 dated changes: the Part A, B and C states, the 1956 States Reorganisation, Goa in 1961, the north-east in 1972, the new states of 2000, Telangana in 2014, the 2019 reorganisation of Jammu and Kashmir, and Kerala becoming Keralam in 2026.
- **Capitals by date:** every state and UT capital as it stood on the chosen date, including summer, winter, second and joint capitals, shared capitals and city renamings (Madras → Chennai, Port Blair → Sri Vijaya Puram, Amaravati's 2026 status and more).
- **Three quiz types:**
  - **Shapes:** drag each state or UT onto the map.
  - **Capitals:** pin each capital city.
  - **Both:** shapes, then capitals.
- **Exam-style prompts:** add your own question to any place, or use the built-in suggestions.
- **Harder modes:** hide the names on the tiles, or hide the borders on the quiz map.
- **Placing pieces:**
  - The piece moves with your pointer at true map size.
  - The cursor turns into a green tick when the piece is over the right spot; on phones the piece glows.
  - A wrong drop sends the piece back.
- **Sharing:** every quiz becomes a short code. Friends paste it under "Join with a code", or open `your-site/#play-<code>`.
- **Ready-made quizzes:** state and UT capitals today, capitals of 1956, the princely unions of 1950, the 1956 reorganisation, and India today.
- **Design:** Apple-style interface with light and dark mode and an onboarding tour, and it works on phones, tablets and desktop.
- **No backend:** a single static page with two data files and no accounts or tracking.

## Project structure

```
index.html            the whole app (HTML, CSS, JS; topojson-client is inlined)
data/districts.json   simplified 2011 census district boundaries (TopoJSON)
data/eras.json        dated reorganisations, place names and types, capitals by date
```

Historical states are built from 2011 district lines, so each date's map is assembled from those districts in the browser.

## Run locally

The page fetches its data files, so serve the folder rather than opening the file directly:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

It's a static site with no build step:

- **Vercel:** import the repo with the framework preset set to "Other" and leave the build settings empty, or run `vercel --prod` in the folder.
- **GitHub Pages / Netlify / Cloudflare Pages:** serve the repo root.

## Data and accuracy

- **Boundaries:** district boundaries come from the [DataMeet](https://github.com/datameet/maps) community and are licensed CC BY 2.5 India. India's outer boundary follows the Survey of India depiction used in Indian textbooks.
- **Approximate historical borders:** these are rebuilt from 2011 district lines, so a few old borders that followed single taluks are approximate (for example Kollegal and Abu Road).
- **Year-level dates:** some capital moves and city renamings are recorded to the year rather than the exact day (for example Gandhinagar in 1970 and Dispur in 1973).
- **Not yet in India:** Portuguese India, French India and Sikkim before 1975 are shown hatched.

Corrections are welcome. Please open an issue with a source.

---

2026 · Built with ❤️ by Shagun
