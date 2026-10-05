
```markdown
# Hostel Maintenance Survey — University of Ibadan

A survey of hostel residents at the University of Ibadan, run in September 2026. 13 questions, 107 responses, covering facility conditions, breakdown frequency, reporting and response times, management perception, and satisfaction.

Analysis is in a Jupyter notebook. The output is a single interactive HTML dashboard that reads from the survey data.

## What's in here

```
.
├── Hostel_Maintenance_Analysis.ipynb   # the analysis
├── data/
│   └── hostel_survey.csv               # raw responses
├── output_figures/                     # charts saved as PNGs
└── report.html                         # the dashboard
```

## Running it

You need Python 3.10+.

```bash
pip install pandas numpy scipy matplotlib seaborn jupyter
jupyter notebook Hostel_Maintenance_Analysis.ipynb
```

Then `Kernel → Restart & Run All`. The final cells write `report.html`.

## The dashboard

`report.html` is a single file. No build step, no server. Open it in a browser and it works.

- Filter sidebar (gender, level, occupancy) — every chart on every tab updates
- Seven tabs, one per survey section
- KPI cards, Pareto chart for priorities, keyword extract from the free-text field
- Responsive — collapses to a single column on mobile
- Prints cleanly to PDF (`Ctrl+P → Save as PDF`)

The same file works as both the submitted report and a live web page. To host it, rename `report.html` to `index.html` and push it to a GitHub Pages branch.

## What I found

- Mean facility condition: 2.51 out of 5. Every facility sits below "Fair".
- Toilets and bathrooms are the lowest-rated item (2.06/5) and the top priority for repair (67%).
- 43.9% of maintenance issues take over a month to resolve.
- 68.2% of respondents are dissatisfied with maintenance.
- Facility condition correlates with satisfaction at r = 0.68.

## Notes on the analysis

- Likert responses are encoded as integers so they can be treated statistically.
- Confidence intervals on the condition means are 95%.
- The chi-square and t-tests in the cross-analysis section use the same 107-respondent sample; subgroup splits get thin, so I flag when numbers stop being reliable.
- Free-text keywords are a quick scan, not thematic coding — useful for a first pass, not a final word.

## Author

Akinwunmi Michael
[github.com/DevPepperspray](https://github.com/DevPepperspray)
```

