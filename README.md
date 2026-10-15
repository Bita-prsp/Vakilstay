# VakilStay — Stay & Explore Shiraz

A responsive bilingual travel and accommodation guide for visitors to Shiraz, Iran. Designed for GitHub Pages:

**https://bita-prsp.github.io/Vakilstay/**

## What's updated in v5

- **Real Persian/English UI switching:** switches the document language and direction (`rtl` for Persian, `ltr` for English), translates the main navigation, headings, travel copy, accommodation/place cards, filters, modal text, labels and live weather output, and persists the visitor's choice in their browser.
- **Weather integrated into the hero glass card:** current temperature and condition, feels-like temperature, humidity, wind, rain probability and a horizontally scrollable seven-day forecast. Weather comes from Open-Meteo; when the network or service is unavailable, an honest error state is shown.
- **Shiraz-local clock and Solar Hijri date:** displays live time, weekday and Persian-calendar date. Public-holiday information is loaded from Persian-Calendar.com; if that service is unavailable, the UI shows that status rather than inventing a holiday.
- **Cards / interactive map tabs for places:** the map uses Leaflet and OpenStreetMap, includes clickable map pins plus a tag list of attractions, and calculates approximate straight-line distance from the stay reference point. Selecting a tag focuses its marker; its popup includes a button to open the full place details.
- **Exact logo filename casing:** logo references now use `images/Logo/Logo.png` to match the case-sensitive path specified for the repository. A fallback mark is used if the logo cannot load.
- Keeps the room cards, reservation links, favourites, place filters, trip planner, gallery, social metadata, PWA setup, sharing and compact visitor stats.

## Important map-location note

The source repo's short Google Maps link could not be resolved to raw coordinates in this build environment. For that reason, `STAY_POINT` in `script.js` is a **clearly labelled approximate central-Shiraz reference**, not a claim that the property pin is exact. The map opens centered on this reference and can open the actual existing Google Maps pin from the map panel. For accurate distances, replace the two coordinates in `STAY_POINT` with the latitude and longitude of the property pin. Attraction coordinates are approximate too; distances are straight-line estimates, not driving or walking distances.

## Logo and repository files

Keep the existing repository file exactly at:

`images/Logo/Logo.png`

GitHub Pages uses case-sensitive paths: `Logo.png` and `logo.png` are different filenames. The ZIP intentionally focuses on the updated site files and its `assets/` folder; when merging it into the existing repo, **do not delete the existing `images/` folder, `guide.pdf`, or real property photos**. The project checks the logo path and falls back to `assets/brand-mark.svg` if it is missing or renamed.

## Publish the update

1. Download and extract `VakilStay-Bita-Prsp-v5.zip` locally.
2. In the `Bita-prsp/Vakilstay` repository, upload/replace `index.html`, `style.css`, `script.js`, `README.md`, `manifest.webmanifest`, and `sw.js` in the repository root, and merge the bundled `assets/` folder with the current one. Keep `images/Logo/Logo.png`, `guide.pdf` and any real room photographs already in your repo.
3. Commit the changes and wait for GitHub Pages to publish.
4. Open `https://bita-prsp.github.io/Vakilstay/`. For a hard refresh on desktop use **Ctrl + F5**. If the site was already installed as a PWA, close/reopen it after the new service worker activates.
5. Check the logo at `https://bita-prsp.github.io/Vakilstay/images/Logo/Logo.png`. If that direct URL returns 404, the repository path or capitalization differs from the path in the code.

## External services

- Weather: [Open-Meteo](https://open-meteo.com/), public forecast API; no API key is embedded in the site.
- Persian date and holidays: [Persian-Calendar.com API](https://www.persian-calendar.com/developers). Public-holiday names depend on that endpoint's data and availability.
- Interactive maps: [Leaflet](https://leafletjs.com/) and [OpenStreetMap](https://www.openstreetmap.org/). These need an internet connection to load the map tiles.
- Page analytics: existing GitHub Page Insights endpoint. The code displays `—` if the endpoint does not return recognized counts; it never fabricates analytics.

## Local preview

Any static web server works. For example, with Python installed, run `python -m http.server 8080` inside the extracted project folder and open `http://localhost:8080/`. The weather, calendar, map tiles and analytics need a network connection.
