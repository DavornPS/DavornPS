# PULSE interactive presentation demo

A single-page website built with HTML5, CSS3 and vanilla JavaScript. No build step, framework, backend, account, API or internet connection is required.

## Launch

Open `index.html` directly in a modern browser. Alternatively, from this folder run:

```sh
python3 -m http.server 4173
```

Then open http://localhost:4173. Keep the `assets` folder beside the three website files; both Poppins fonts are local.

## Present the demo

1. Start with Apex Creative Studio under normal monitoring.
2. Click **Simulate Emerging Risk**. The four metrics update and the illustrative **Analyst Review & Actions** drawer opens automatically.
3. Close the drawer (close button, Escape or backdrop) to explore the evidence and recommended actions. Select any KPI for its value, comparison, source and explanation. Expand an action to read its rationale.
4. **Reopen Analyst Review** opens the drawer again. Its optional checkboxes mark priorities **Under Review** locally; no real action occurs.
5. Click **Reset Demo** to restore baseline values, included sources, collapsed details, routine recommendations and starting activity.

The same scenario controls the business example further down the page. Pricing buttons select a proposed plan and explain its support level; they do not initiate a purchase.

### Missing-data example

In **Connections**, expand **Inspect data coverage** and switch off **Accounting data**. Payment time, largest client share and operating costs become unavailable, their dependent recommendations are removed, and the combined warning is withheld. Only the CRM pipeline remains assessable. The case study and analyst example respect the same missing-source state. Restore the switch or reset to return to full coverage. Project-management input is clearly labelled as unused in this assessment.

## Fictional information and scope

All company information, business figures, period comparisons, activity and analyst insight are fictional. There are no live connections, actual customer records, real analysts, automated management decisions or financial forecasts. Values are deterministic and reset on reload. Analyst checklist selections are local to this page session.

| Signal | Baseline | Emerging risk | Change |
|---|---:|---:|---:|
| Sales pipeline | $38,000 | $21,000 | −45%, rounded |
| Average payment time | 24 days | 41 days | +17 days |
| Largest client share | 28% | 46% | +18 percentage points |
| Monthly operating costs | approximately $21,600 | $24,000 | +11%, rounded |

The charts connect two supplied period observations only. They do not imply intermediate measurements or predictions. Baseline comparison values equal baseline current values to establish the calm demonstration state.

Proposed launch pricing for Cambodian SMEs. Subject to validation through paid customer pilots. All prices are in USD:

| Plan | Monthly subscription | One-time setup fee | Human support |
|---|---:|---:|---|
| PULSE Monitor | $129 | $99 | Software monitoring and recommendations; no regular human analyst support |
| PULSE Explorer | $299 | $199 | Scheduled monthly analyst review, priority risk support and deeper action planning |
| PULSE Advisory | $599 | $399 | Expanded proactive analyst involvement and management reviews; optional additional advisory services subject to scope |

No checkout or real subscription service exists here.

## Visual reference and accessibility

The supplied `PULSE (1).pdf`, `PULSE Analyst Review Dashboard.png` and `Apex Creative Studio Analytics Dashboard.png` were inspected visually. The page retains the deck's Poppins typeface, deep blue, turquoise, sky-blue gradient and light dashboard treatment. Full Poppins Regular and SemiBold fonts are self-hosted with their SIL Open Font License in `assets/OFL.txt`; no substitute typeface was needed. The wordmark uses a simple CSS bar motif inspired by the supplied dashboards. The interface is rebuilt with semantic HTML, CSS and SVG, not screenshots.

Native modal dialogs provide keyboard focus containment, Escape dismissal and focus restoration. Navigation, details disclosures, checkboxes and switches support the keyboard. Reduced motion is respected. Charts have text alternatives and all missing data has explicit labels.

Supported target: modern Chrome, Safari, Edge and Firefox with native `dialog` support. This is a presentation of a proposed product, not an operational risk-monitoring or financial-advice service.

## Verification completed

- Chromium functional checks: initial values, all four KPI dialogs, risk scenario, warning disclaimer, four recommendation disclosures, analyst close/reopen, local review checklist and full reset.
- Missing-source checks across the dashboard, metric details, case study, recommendations and analyst example.
- All main navigation links, mobile menu, all three plan interactions and final CTA focus.
- Normal, risk and analyst-drawer layouts at 1440×900, 1280×800, 768×1024, 390×844 and 320×844, with screenshots and horizontal-overflow checks.
- Keyboard focus containment and restoration, Escape dismissal and reduced-motion behaviour.
- Direct `file://` opening and no browser console or script errors.
- Axe WCAG 2 A/AA and 2.1 AA automated scans: no violations reported in normal, risk, analyst, missing-data, metric-dialog and 320px missing-data states after contrast fixes. Automated scanning does not replace a full manual accessibility audit.

`qa.cjs` is the optional developer regression script, using Playwright available in the development environment. It expects the static server on port 4173 and writes screenshots/results to `/tmp`; it is not required to run or present the website. Safari and Firefox were not separately tested.

### Cambodia pricing update verification

The existing `node qa.cjs` regression suite and `node --check script.js` passed after the pricing update. Additional Chromium checks verified all monthly prices, setup fees, exact plan descriptions and feature lists, selection messages, disclaimer, plan order and featured Explorer at 1440, 1280, 768, 390 and 320 pixels wide. No obsolete subscription prices, content overflow, JavaScript errors or browser console errors were found. Desktop, tablet and mobile pricing screenshots were inspected visually.

Only pricing-section markup, plan-selection copy and a setup-fee style changed in the website files. Dashboard markup, simulation logic and all existing CSS rules were preserved exactly.

## Publish to GitHub Pages

1. Upload or commit the updated `index.html`, `styles.css` and `script.js` to your website repository's publishing folder. Keep `assets/` beside them. Include `README.md` if maintaining this documentation in the repository.
2. For branch-based publishing, open the repository's **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select the publishing branch and **/(root)** (or the existing **/docs** folder), then **Save**.
3. Wait for the Pages deployment to finish, open the published URL shown in Pages settings, and refresh to check pricing and the demo.

If Pages already uses a GitHub Actions workflow, commit to its configured source branch and keep the existing deployment setup. This local folder currently has no Git repository metadata; upload the files to the existing website repository or clone that repository before using Git commands here.

See the [GitHub Pages publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
