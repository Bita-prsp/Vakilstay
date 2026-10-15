# VakilStay — Stay & Explore Shiraz

A responsive bilingual travel and accommodation guide for visitors to Shiraz, Iran. Designed for GitHub Pages:

**https://bita-prsp.github.io/Vakilstay/**

## What's updated in v6

- **Real Persian/English UI switching:** switches the document language and direction (`rtl` for Persian, `ltr` for English), translates the main navigation, headings, travel copy, accommodation/place cards, filters, modal text, labels and live weather output, and persists the visitor's choice in their browser.
- **Weather integrated into the hero glass card:** current temperature and condition, feels-like temperature, humidity, wind, rain probability and a horizontally scrollable seven-day forecast. Weather comes from Open-Meteo; when the network or service is unavailable, an honest error state is shown.
- **Shiraz-local clock and Solar Hijri date:** displays live time, weekday and Persian-calendar date. Public-holiday information is loaded from Persian-Calendar.com; if that service is unavailable, the UI shows that status rather than inventing a holiday.
- **Mobile-first responsive layout:** rebuilt responsive overrides for small Android and iPhone widths, including iPhone 11 Pro-class screens. Room cards stack vertically on phones, filters become horizontally scrollable chips, buttons and modal actions fit the viewport, and the fixed contact bar respects iOS safe areas.
- **Exact property pin and nearby essentials:** property coordinates are set from the supplied pin. The map has separate clickable markers for Vakil Subway Station and Shahid Beheshti Hospital, plus their calculated straight-line distances from the stay.

## Confirmed coordinates and distances

The accommodation pin uses the exact coordinates supplied for the property:

- **VakilStay:** `29.6129444444, 52.5529166667` (`29°36'46.6"N 52°33'10.5"E`)
- **Vakil Subway Station:** `29.6127222222, 52.5515000000` (`29°36'45.8"N 52°33'05.4"E`) — approximately **139 m straight-line** from the accommodation.
- **Shahid Beheshti Hospital:** `29.6112500000, 52.5554444444` (`29°36'40.5"N 52°33'19.6"E`) — approximately **309 m straight-line** from the accommodation.

These distances are calculated from the provided coordinates using the great-circle distance formula. They are not walking or driving distances. Existing tourist-attraction coordinates are approximate and their distances should be treated as estimates. The map opens at the precise property coordinates and makes the two nearby service markers separately selectable.

## Logo and repository files

Keep the existing repository file exactly at:

`images/Logo/Logo.png`

GitHub Pages uses case-sensitive paths: `Logo.png` and `logo.png` are different filenames. The ZIP intentionally focuses on the updated site files and its `assets/` folder; when merging it into the existing repo, **do not delete the existing `images/` folder, `guide.pdf`, or real property photos**. The project checks the logo path and falls back to `assets/brand-mark.svg` if it is missing or renamed.

## Publish the update

1. Download and extract `VakilStay-Bita-Prsp-v6.zip` locally.
2. In the `Bita-prsp/Vakilstay` repository, upload/replace `index.html`, `style.css`, `script.js`, `README.md`, `manifest.webmanifest`, and `sw.js` in the repository root, and merge the bundled `assets/` folder with the current one. Keep `images/Logo/Logo.png`, `guide.pdf` and any real room photographs already in your repo.
3. Commit the changes and wait for GitHub Pages to publish.
4. Open `https://bita-prsp.github.io/Vakilstay/`. For a hard refresh on desktop use **Ctrl + F5**. If the site was already installed as a PWA, close/reopen it after the new service worker activates.
5. Check the logo at `https://bita-prsp.github.io/Vakilstay/images/Logo/Logo.png`. If that direct URL returns 404, the repository path or capitalization differs from the path in the code.

## External services

- Weather: [Open-Meteo](https://open-meteo.com/), public forecast API; no API key is embedded in the site.
- Persian date and holidays: [Persian-Calendar.com API](https://www.persian-calendar.com/developers). Public-holiday names depend on that endpoint's data and availability.
- Interactive maps: [Leaflet](https://leafletjs.com/) and [OpenStreetMap](https://www.openstreetmap.org/). These need an internet connection to load the map tiles.
- Page analytics: existing GitHub Page Insights endpoint. The code displays `—` if the endpoint does not return recognized counts; it never fabricates analytics.

## Mobile check

After publishing, check the page at around 375 × 812 px (iPhone 11 Pro CSS viewport), 390 × 844 px, and a smaller 320 px viewport. Check both Persian RTL and English LTR, open the interactive map tab, and open a place-detail modal. The map tiles and online weather/calendar endpoints require an internet connection.

## Local preview

Any static web server works. For example, with Python installed, run `python -m http.server 8080` inside the extracted project folder and open `http://localhost:8080/`. The weather, calendar, map tiles and analytics need a network connection.
