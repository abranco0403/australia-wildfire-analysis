# Australia Wildfire Activity Analysis
### Fifteen years of NASA satellite data — examined for risk patterns across seven regions

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white&style=flat-square)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white&style=flat-square)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?logo=plotly&logoColor=white&style=flat-square)
![Dash](https://img.shields.io/badge/Dash-00B4D8?style=flat-square)
![Folium](https://img.shields.io/badge/Folium-77B829?style=flat-square)

---

## What This Project Is

An end-to-end exploratory analysis of wildfire activity across Australia's seven regions, using daily satellite fire observations from NASA's FIRMS system (2005–2020). The goal was to answer three questions a risk analyst or policy team would actually care about:

1. **How has wildfire severity changed over time — and is 2019–20 truly an outlier?**
2. **Which regions carry the most fire risk, and by how much?**
3. **How reliable is the satellite detection data at the extremes that matter most?**

The analysis is presented as a [self-contained HTML report](Australia_Wildfire_Analysis_Report.html) that any stakeholder can open without Python, and backed by a fully reproducible Jupyter notebook with an interactive Dash dashboard.

---

## Key Findings

**The 2019–20 Black Summer was a structural break, not just a bad year.**
Annual average fire area in 2019–20 far exceeded any prior year in the dataset — not the continuation of a gradual upward trend, but a step-change event. Risk models that assume linear trends will systematically underestimate tail exposure.

**Queensland and the Northern Territory dominate the risk profile.**
Together they account for roughly 58% of all fire pixel detections across the dataset, and show consistently above-average fire brightness (intensity). The remaining five regions share the other 42%, with Tasmania and Victoria having the lowest spatial footprint despite historically high human impact.

**Seasonality is predictable — and actionable.**
December through February drive peak fire activity every year, regardless of annual severity. This creates a clear and reliable window (October–November) for preemptive resource deployment.

**More intense fires are detected with slightly higher confidence (r ≈ +0.28).**
The weak positive correlation between radiative power and detection confidence means the data is marginally more reliable precisely where it matters most — at high-intensity extremes.

---

## Repository Structure

```
australia-wildfire-analysis/
│
├── Australia_Wildfire_Analysis_Report.html   # Full analytical report — open in any browser
├── Australia_Wildfire_Analysis.ipynb         # Reproducible notebook — all code and charts
├── app.py                                    # Standalone Dash dashboard
├── requirements.txt                          # Pinned dependencies
└── README.md
```

**Start with the HTML report** if you want to understand the analysis and findings.
**Open the notebook** if you want to see the code, reproduce the charts, or adapt the work.

---

## Running the Project

**Prerequisites:** Python 3.9+

```bash
# Install dependencies
pip install -r requirements.txt

# Run the full analysis notebook
jupyter notebook Australia_Wildfire_Analysis.ipynb

# Or launch the interactive dashboard
python app.py
# → http://127.0.0.1:8050
```

The notebook fetches the dataset automatically from the NASA/IBM public URL — no manual download needed.

---

## Dashboard

The Dash dashboard lets you explore the data interactively — select any region and year to see:
- Monthly distribution of average estimated fire area (donut chart)
- Monthly average fire pixel count (bar chart)

Both charts update in real time. Useful for comparing how a specific season played out across different regions.

---

## Data

**Source:** NASA Fire Information for Resource Management System (FIRMS) — MODIS Collection 6
**Distributed by:** IBM Skills Network for educational use
**Coverage:** 2005–2020 · 7 Australian regions · Daily aggregations · Confidence threshold > 75%

| Variable | Description | Unit |
|----------|-------------|------|
| `Region` | NSW, QL, SA, TA, VI, WA, NT | — |
| `Estimated_fire_area` | Daily sum of confirmed fire area | km² |
| `Mean_estimated_fire_brightness` | Average fire pixel temperature | Kelvin |
| `Mean_estimated_fire_radiative_power` | Average energy released by fires | MW |
| `Mean_confidence` | Average detection confidence | % |
| `Count` | Number of fire pixels detected | pixels |
| `Replaced` | Updated with higher-quality data | Y / — |

---

## Tools

Python · Pandas · NumPy · Matplotlib · Seaborn · Folium · Plotly · Dash

---

## Author

**[Your Name]**
Data Analyst · [LinkedIn](https://linkedin.com/in/yourprofile) · [yourname@email.com](mailto:yourname@email.com)
