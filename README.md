# Movie Ratings Bar Chart — Plotly + D3

## Summary
##### A minimal, single-page app that loads a small movie dataset and renders an interactive **bar chart** with **Plotly**, using **D3** to fetch local JSON. The HTML includes a `div#bar-plot` mount point and CDN links to Plotly and D3, with chart logic in `plot.js`. 
---

## Goal
- Demonstrate a clean pattern for **loading JSON data with D3** and **plotting with Plotly** in a static page.
- Provide a starter template you can extend into richer dashboards (sorting, filters, multiple traces).

---

## Procedure
1. **Page scaffold**  
   Define a container `<div id="bar-plot"></div>`, include Plotly and D3 from CDNs, and load `plot.js`. 
2. **Data source**  
   Store records in `data.json` with fields such as `title`, `year`, `imdbRating`, and `metascore`. 
3. **App logic (plot.js)**  
   Use **D3** to read `data.json`, map fields, and build Plotly traces/layout; render into `#bar-plot`. (Script referenced in HTML.) 
4. **(Optional) Hosting**  
   The repo is set up for GitHub Pages via Jekyll theme config. 

---

## Result
- A working **bar chart** of movies from `data.json`, rendered into the `#bar-plot` container using Plotly. 
- Dataset example (top entry): `"The Shawshank Redemption"` (1994), `imdbRating: 9.3`, `metascore: 80`. 

---

## Business Impact
- **Faster prototyping:** Simple scaffold to validate a data story before investing in a full app.
- **Reusable template:** Swap in any JSON (KPIs, sales, survey results) and keep the same rendering pattern.
- **Stakeholder-friendly:** Plotly defaults (tooltips/legends) make insights accessible without extra code.

---

## Next Steps to Make It Better
1. **Interactions:** Add sorting (e.g., by IMDb rating), hover templates, and click-to-filter.
2. **Multiple metrics:** Toggle between `imdbRating` and `metascore`; add dual-axis or grouped bars.
3. **Data validation:** Check for missing fields, normalize titles, and fix typos (e.g., “Schindeler’s List”). 
4. **Styling & layout:** Add a title, axis labels, and responsive sizing; extract styles into a CSS file.
5. **Ops:** Split code into modules, add a simple linter/test, and auto-deploy to GitHub Pages.

---

## Run Locally
```bash
# Serve files to avoid CORS issues with local JSON
python -m http.server 8000
# then open in your browser:
http://localhost:8000/index.html
````

## Project Structure

```
.
├── index.html     # includes Plotly & D3 CDNs, and <div id="bar-plot">
├── plot.js        # loads data.json with D3 and renders Plotly bar chart
├── data.json      # movie records: title, year, imdbRating, metascore
└── _config.yml    # (optional) GitHub Pages theme
```
