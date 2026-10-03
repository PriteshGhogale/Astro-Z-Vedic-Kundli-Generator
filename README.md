# 🔯 Astro-Z Vedic Kundli Generator

A free, single-page Vedic (Jyotish) astrology web app that generates a sidereal birth chart — along with planetary strength analysis, Panchang, and Vimshottari Dasha periods — entirely in the browser. No backend, no database, no build step.

**Live demo:** _add your deployed URL here after publishing_

---

## ✨ Features

- **Birth details form** — name, date, time, and birth place (type any city — coordinates are auto-fetched via live geocoding, with a built-in offline city list as a fallback)
- **North Indian & South Indian chart styles** — toggle between both traditional layouts for the Rasi (D1) chart
- **Navamsa (D9) chart** — the key divisional chart for marriage and refined planetary strength
- **Planetary status flags** — Retrograde (℞), Combust (c), Exalted (↑), Debilitated (↓)
- **Sign-wise strength** — Exalted → Own Sign → Friendly Sign → Neutral Sign → Enemy Sign → Debilitated, based on the classical Naisargika Maitri (natural friendship) table
- **Panchang at birth** — Tithi, Nitya Yoga, Karana, and Vara (weekday)
- **Vimshottari Mahadasha** — full 120-year period table, with an optional Antardasha (sub-period) breakdown for the current period
- **Interpretive paragraphs** — short auto-generated notes per planet based on house and sign placement
- **Downloadable PDF report** — cover summary, both D1/D9 charts (your choice of North or South Indian style), full planet table, Mahadasha/Antardasha tables, sign-wise strength table, and interpretations — all as properly formatted tables

## 🧮 How it works

All astronomical calculations run client-side in JavaScript:

- Sun, Moon, and planetary longitudes from simplified mean-orbit (Keplerian) formulas
- Lahiri ayanamsa for sidereal conversion
- Ascendant (Lagna) from local sidereal time and standard spherical trigonometry
- Vimshottari Dasha derived from the Moon's nakshatra at birth

**Accuracy note:** these are simplified astronomical formulas, not a full ephemeris (like Swiss Ephemeris). They're accurate to roughly sign/nakshatra level for most dates — great for exploration, not a substitute for professional-grade software for critical use cases.

## 🛠️ Tech Stack

- Plain HTML, CSS, and vanilla JavaScript — no frameworks, no build tools
- [jsPDF](https://github.com/parallax/jsPDF) + [jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable) (loaded via CDN) for the downloadable PDF report
- [Nominatim (OpenStreetMap)](https://nominatim.org/) for live place-name geocoding

## 🚀 Deploy / Run

This is a single `index.html` file — any static host works.

**Option A — Netlify (fastest)**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag `index.html` in → get a live URL instantly

**Option B — GitHub Pages (this repo)**
1. Go to **Settings → Pages**
2. Under "Branch," select `main` and `/ (root)` → **Save**
3. Your site will be live at `https://<your-username>.github.io/Astro-Z-Vedic-Kundli-Generator/`

**Option C — Run locally**
Just open `index.html` in any browser. No server required.

> **Note:** Live place-name lookup (geocoding) requires network access to `nominatim.openstreetmap.org`, so it works once deployed to a real host, but not from a `file://` path in every browser due to CORS. The built-in city dropdown works everywhere, including offline.

## 📂 Project Structure

```
.
├── index.html      # The entire app — HTML, CSS, and JS in one file
├── README.md
└── LICENSE
```

## ⚖️ Disclaimer

This tool is intended for educational and entertainment purposes. Calculations use simplified astronomical approximations and should not be relied upon for medical, legal, financial, or other high-stakes decisions.

## 📄 License

MIT — see [LICENSE](LICENSE).
