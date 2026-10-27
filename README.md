# 🏎️ F1 Race Intelligence Dashboard

An interactive **Tableau dashboard project** for exploring Formula 1 race results, constructor performance, driver standings, podium finishes, tyre-compound outcomes, and race reliability.

## 📌 Project Overview

The F1 Race Intelligence Dashboard brings key race-performance indicators into a single place to help users explore patterns across seasons, drivers, constructors, circuits, and race outcomes.

This repository includes the packaged Tableau workbook and project documentation in PowerPoint, PDF, and Word formats.

## 🎯 Objectives

- Explore constructor points and performance trends across seasons.
- Compare driver points and podium finishes.
- Review tyre-compound outcomes across circuit types.
- Investigate retirements and DNF patterns by team.
- Summarize race-host countries and circuit information.
- Present findings in a dashboard that is easy to explore and share.

## 📊 Dashboard Contents

### Dashboard 1 — F1 Race Intelligence

- **Constructor Points Trend:** points by season and constructor.
- **Tyre Compound Outcomes:** points by starting tyre compound, segmented by circuit type.
- **DNF Reasons by Team:** retirements grouped by team and reason.
- **Podiums by Driver:** podium finishes by driver.

### Dashboard 2 — Broadcast & Reliability

- **Driver Points Leaderboard:** total points by driver.
- **Grand Prix Hosts by Country:** distinct race-event count by country.
- **Driver Reliability by Driver:** average DNF flag, interpreted as a row-level DNF-rate proxy.
- **Podiums by Driver:** podium finishes by driver.

## 🗂️ Dataset Summary

The source workbook contains these worksheets:

| Worksheet | Rows |
|---|---:|
| `race_results` | 6,464 |
| `championship_standings` | 311 |
| `lap_intelligence` | 3,814 |
| `qualifying_results` | 3,130 |
| `circuits` | 29 |

The `race_results` worksheet covers seasons **2010–2026**. The mapped race data identifies **334 unique race events**.

> **Data note:** Row counts describe the source workbook used when this project documentation was prepared. They may differ if the data is refreshed or modified.

## 🧮 Data Mapping and Metrics

| Dashboard field | Source or rule |
|---|---|
| Race ID | `race_id` |
| Grand Prix / Circuit | `circuit_name` (used as the available event/circuit label) |
| Circuit Country | `country` |
| Circuit Type | `circuit_type` |
| Tyre Compound | `starting_compound` |
| Podium Flag | `1` when `finish_position` is 1, 2, or 3 |
| Winner Flag | `1` when `finish_position` is 1 |
| DNF Flag | `dnf` |
| Status | DNF when `dnf = 1`; otherwise Finished |

### Suggested calculated fields

These formulas are examples; confirm field names and data types in Tableau before using them.

```tableau
// DNF Rate
SUM([DNF Flag]) / COUNT([Race ID])
```

```tableau
// Podium Count
SUM([Podium Flag])
```

```tableau
// Points per Start
SUM([Points]) / COUNT([Race ID])
```

```tableau
// Average Positions Gained (if the field exists)
AVG([Positions Gained])
```

## 🛠️ Tools

- **Tableau** — dashboard development and data visualization.
- **Microsoft PowerPoint** — project presentation.
- **Microsoft Word** — editable project documentation.
- **PDF** — portable report format.
- **GitHub** — version control and project sharing.

## 📁 Repository Structure

Suggested layout:

```text
F1-Race-Intelligence-Dashboard/
├── F1_Race_Intelligence_UserData_Recolored.twbx
├── F1_Race_Intelligence_Project.pptx
├── F1_Race_Intelligence_Project.pdf
├── F1_Race_Intelligence_Project.docx
└── README.md
```

The `.twbx` file is a packaged Tableau workbook and may contain embedded data extracts or supporting resources.

## 🚀 How to Open the Dashboard

1. Download or clone this repository.
2. Install and open Tableau Desktop or a compatible Tableau application.
3. In Tableau, select **File → Open**.
4. Open `F1_Race_Intelligence_UserData_Recolored.twbx`.
5. If Tableau prompts you to upgrade the workbook, review the prompt and proceed if appropriate.
6. Confirm the data source is available and that worksheets and dashboards render correctly.

## ⚠️ Known Limitations

- Driver nationality and team nationality are not supplied in the uploaded workbook; nationality fields are left blank and are not used in the dashboards.
- The available `circuit_name` field is used as the Grand Prix/circuit label because a separate official event-name field is not available.
- Driver reliability is represented by an average DNF flag and should be interpreted as a row-level DNF-rate proxy, not as a complete engineering reliability measure.
- Validate the workbook in Tableau Desktop after opening it, especially if your Tableau version or data source differs from the original environment.

## 📄 Project Documentation

- **Presentation:** `F1_Race_Intelligence_Project.pptx`
- **PDF report:** `F1_Race_Intelligence_Project.pdf`
- **Editable report:** `F1_Race_Intelligence_Project.docx`

## 🔒 Data and Licensing

Before making this repository public, confirm that you have permission to redistribute the underlying dataset and any third-party assets. Add the applicable source attribution or license information here. Do not claim a dataset license unless you have verified it.

## 👤 Author

Add your name, portfolio link, or contact details here if you want to identify yourself as the project author.

---

**Built for Formula 1 data exploration and Tableau dashboard storytelling.**
