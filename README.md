
# Supplement Intelligence Engine Pro

A privacy-first, single-page supplement research dashboard for exploring supplements, comparing evidence signals, checking safety cautions, building stacks, saving notes, and exporting reports.

> **Important:** This project is for educational and informational use only. It does not diagnose, treat, cure, prevent disease, or replace advice from a qualified clinician, pharmacist, dietitian, or other healthcare professional.

---

## Overview

**Supplement Intelligence Engine Pro** is an advanced browser-based supplement explorer built as a single HTML file. It helps users search and compare supplements by category, brain-support scores, evidence strength, safety risk, goals, form, price, and more.

The app includes a local curated supplement database, optional external-source enrichment, bookmarks, notes, a stack builder, pairwise caution checks, CSV/JSON export, shareable local-state links, and print-ready reports.

It is designed to be easy to run, easy to modify, and privacy-friendly because most data is stored locally in the browser.

---

## Features

### Supplement Search

- Search by supplement name
- Search by brand
- Search by category
- Search by ingredients
- Search by benefits
- Search by mechanisms
- Search by safety notes
- Clear-search button
- Debounced search for smoother performance

### Category Filters

Filter supplements by:

- Nootropics
- Vitamins
- Minerals
- Herbal
- Amino Acids
- Protein

### Advanced Filters

The advanced filter panel includes:

- Neural Genesis score
- Neuroplasticity score
- Cognitive Boost score
- Evidence score
- Maximum safety risk
- Supplement form
- Budget range
- Goal preset

Goal presets include:

- Focus and memory
- Stress support
- Sleep and recovery
- Training recovery

### External Source Controls

The app keeps the original external-source style controls:

- Local Database
- Open Food Facts
- Examine.com compatibility enrichment
- PubMed search ID enrichment
- NIH ODS-style safety enrichment
- Master External APIs toggle

Open Food Facts and PubMed are real optional fetch-based integrations. Examine.com and NIH ODS are retained as compatibility/enrichment controls rather than fake API endpoints.

### Sorting

Sort results by:

- Relevance
- Brain Fit
- Evidence
- Lowest Risk
- Rating
- Price Low
- Price High
- Name A-Z
- Neural Genesis
- Neuroplasticity
- Cognitive Boost

### Views and Pagination

- Grid view
- List view
- Items per page selector
- Pagination controls
- Responsive card layout

### Supplement Detail Modal

Each supplement opens into a detailed modal with tabs for:

- Overview
- Brain Profile
- Ingredients
- Evidence
- Safety
- Notes
- Compare

### Brain-Support Profile

Each supplement includes three main brain-support scores:

- **Neural Genesis**
- **Neuroplasticity**
- **Cognitive Boost**

These are educational heuristic scores, not medical claims.

### Evidence and Risk Scoring

Each supplement includes:

- Evidence score
- Evidence level
- Risk level
- Research notes
- Mechanism tags
- Safety tags
- Interaction reminders

### Smart Insight Panel

The Smart Insight panel summarizes:

- Current top match
- Evidence score of the top result
- Risk level of the top result
- Average evidence across filtered results
- Number of caution-flagged results

Quick buttons include:

- High evidence
- Low risk
- Clear boosts

### Bookmarks

- Save supplements locally
- Remove saved supplements
- Filter to bookmarks only
- Export bookmarks as JSON

### Stack Builder

The stack builder lets users compare multiple supplements together.

Features include:

- Add/remove stack items
- Stack radar chart
- Average stack profile
- Safety summary
- Pairwise conflict matrix
- Stack alert count
- Copy stack summary
- Clear stack

### Pairwise Conflict Matrix

The app checks selected stack items for shared local caution tags, such as:

- Sedatives
- Blood thinners
- Kidney condition
- Pregnancy/breastfeeding
- Under 18
- Surgery planned

This is only a local warning heuristic and should not be treated as a full interaction checker.

### Safety Profile Flags

Users can select personal safety context flags, stored locally:

- Pregnant / breastfeeding
- Under 18
- Blood thinners
- SSRIs / antidepressants
- Sedatives
- Blood pressure meds
- Kidney condition
- Surgery planned

The app uses these flags to highlight possible caution matches.

### Personal Notes

Each supplement includes a notes tab.

Notes are:

- Stored locally in the browser
- Saved per supplement
- Included in JSON export
- Useful for tracking questions, experiences, or clinician/pharmacist follow-up points

### Dose / Trial Planner

The stack builder includes a simple trial planner with:

- Schedule selector
- Trial length selector
- Copy dose plan button

Schedule options:

- Follow label
- Morning
- Evening
- Around training
- Split AM/PM

Trial lengths:

- 2 weeks
- 4 weeks
- 8 weeks
- 12 weeks

### Export and Reporting

The app supports:

- JSON bookmark export
- CSV results export
- Copy stack summary
- Copy dose plan
- Copy supplement summary
- Print supplement report
- Shareable local-state link

### Theme and Preferences

- Dark mode
- View preference persistence
- Page-size persistence
- Bookmark persistence
- Stack persistence
- Notes persistence
- Safety profile persistence
- Dose-plan persistence

All saved using `localStorage`.

### Built-in Tests

The app includes a small built-in console test runner.

It checks:

- Supplement dataset presence
- CSV escaping
- Risk label mapping
- Duplicate removal
- Search/filter behavior

Open the browser console and look for:

```text
Supplement Explorer tests passed: 5
````

---

## Demo

Open the `index.html` file directly in a browser.

No build step is required.

---

## Installation

### Option 1: Run Locally

1. Download or clone the project.
2. Save the main file as `index.html`.
3. Open `index.html` in a modern browser.

```bash
git clone https://github.com/your-username/supplement-intelligence-engine-pro.git
cd supplement-intelligence-engine-pro
```

Then open:

```text
index.html
```

### Option 2: Use a Local Dev Server

A local server is recommended for best API behavior.

Using Python:

```bash
python -m http.server 8080
```

Then visit:

```text
http://localhost:8080
```

Using Node:

```bash
npx serve .
```

---

## File Structure

This project is designed as a single-file web app.

```text
.
├── index.html
└── README.md
```

The `index.html` file contains:

```text
HTML structure
CSS styling
JavaScript state management
Supplement dataset
Search/filter logic
Modal rendering
Stack builder
Export tools
Safety checker
Built-in tests
```

---

## Technologies Used

* HTML5
* CSS3
* Vanilla JavaScript
* Chart.js
* Font Awesome
* Google Fonts
* Open Food Facts API
* PubMed E-utilities API
* Browser localStorage
* Browser Clipboard API
* Browser Blob/File export APIs

---

## API Notes

### Open Food Facts

Open Food Facts is used for optional external product discovery.

The app searches:

```text
https://world.openfoodfacts.org/cgi/search.pl
```

External product data may be incomplete. Users should verify:

* Ingredient labels
* Serving sizes
* Supplement facts
* Warnings
* Manufacturer information

### PubMed

PubMed E-utilities are used to retrieve related PubMed IDs for a search query.

The app uses:

```text
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi
```

Returned PubMed IDs are only search hints. They are not automatic proof that a supplement is effective or safe.

### Examine.com and NIH ODS

The original project included mock-style Examine.com and NIH API source controls. This upgraded version keeps those controls for feature compatibility but implements them as local enrichment/safety-note behavior rather than calling fake endpoints.

---

## How to Use

### Search Supplements

Type into the search bar to filter supplements by name, brand, benefit, ingredient, mechanism, or safety note.

Example searches:

```text
creatine
magnesium
sleep
focus
blood thinner
stress
protein
```

### Use Category Filters

Click a category chip to filter by supplement type.

Click again to remove the filter.

### Use Advanced Filters

Click:

```text
Advanced Filters
```

Then adjust:

* Brain-support thresholds
* Evidence threshold
* Risk limit
* Form
* Budget
* Goal preset

### Save Bookmarks

Click the bookmark icon on any supplement card.

Bookmarked supplements are saved locally.

### Build a Stack

Click the stack/layer icon on supplement cards.

The stack builder will show:

* Selected supplements
* Radar chart
* Safety alerts
* Pairwise conflict matrix

### Add Notes

Open a supplement detail modal, go to the **Notes** tab, and write your notes.

Notes are saved locally.

### Export Data

Use the top-right buttons:

* JSON export for bookmarks and notes
* CSV export for current results
* Share link for current local state
* Print report for stack/top results

---

## Safety Disclaimer

This project is not a medical tool.

Supplement safety depends on many factors, including:

* Age
* Pregnancy or breastfeeding
* Medical conditions
* Current medications
* Dose
* Product quality
* Allergies
* Surgery plans
* Lab results
* Nutrient status
* Duration of use

Always consult a qualified healthcare professional before starting, stopping, or combining supplements, especially if taking medication or managing a health condition.

---

## Privacy

This app is designed to be privacy-friendly.

Stored locally:

* Bookmarks
* Notes
* Stack items
* Theme preference
* View preference
* Safety profile flags
* Dose-plan settings

The app does not require an account.

External API searches may send the search query to third-party services when API enrichment is enabled.

To avoid external requests:

1. Turn off **External APIs**
2. Use only the local database

---

## Browser Support

Recommended browsers:

* Chrome
* Edge
* Firefox
* Safari

Some features require modern browser APIs:

* Clipboard API
* Blob downloads
* localStorage
* Fetch API
* Canvas rendering for Chart.js

---

## Built-in Test Coverage

The app includes basic runtime tests in the console.

Current tests check:

```text
dataset has supplements
CSV cell escapes comma and newline
risk text maps values
dedupe removes duplicate names
filter search finds creatine
```

These tests are intentionally lightweight and run automatically on load.

---

## Customization

### Add a New Supplement

Add a new `makeSupplement(...)` entry inside the `SUPPLEMENTS` array.

Example:

```js
makeSupplement(
  'example-id',
  'Example Supplement',
  'Example Brand',
  'nootropic',
  'Capsules',
  'image-url',
  24.99,
  4.5,
  100,
  30,
  'b',
  1,
  ['Focus', 'Memory'],
  'Ingredient list here',
  { 'Main Ingredient': 300 },
  'Follow label instructions.',
  'Description here.',
  6,
  7,
  8,
  6.5,
  'Moderate',
  2,
  ['Mechanism 1', 'Mechanism 2'],
  ['focus'],
  ['pregnancy'],
  ['Safety note here.']
)
```

### Add a New Category

Update:

```js
CATEGORY_LABELS
```

Then add supplements using that category key.

### Add a New Safety Flag

Update:

```js
PROFILE_FLAGS
```

Then add that flag to relevant supplement `safetyTags`.

### Change the Theme

Edit the CSS variables inside:

```css
:root
body.dark-mode
```

---

## Known Limitations

* This is not a full medical interaction checker.
* Brain scores are heuristic and educational.
* Product pricing is sample/mock pricing unless imported externally.
* External product data may be incomplete.
* PubMed IDs are search hints, not validated study summaries.
* Examine.com and NIH controls are compatibility enrichment controls, not live official API clients.
* Notes and bookmarks are browser-local and may be lost if browser storage is cleared.

---

## Roadmap

Possible future upgrades:

* Full PWA offline mode
* Import/export full user state
* More detailed clinical evidence grading
* Dose range database
* Interaction severity database
* Supplement quality scoring
* Lab-value tracking
* QR code sharing
* IndexedDB storage
* Full-text research summaries
* Multi-language support
* Accessibility audit
* Unit test page
* Optional backend sync
* Product label scanner
* Barcode scanner
* Timeline-based supplement tracker

---

## Development Notes

This project intentionally uses vanilla JavaScript to keep it portable.

There is no required build system, framework, package manager, or backend.

That makes it easy to:

* host on GitHub Pages
* copy into a static site
* run offline with local data
* modify quickly
* debug in the browser

---

## Contributing

Contributions are welcome.

Good areas to improve:

* Accessibility
* Evidence scoring
* Safety rules
* UI polish
* Dataset quality
* API integrations
* Test coverage
* Documentation
* Mobile usability

Before contributing health-related claims, include reliable sources and avoid overstating evidence.

---

## License

MIT License

You are free to use, modify, and distribute this project, provided the original license is included.

---

