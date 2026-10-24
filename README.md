# Cyclistic Bike-Share Analysis: Annual Members vs. Casual Riders

A case study analysing how **annual members** and **casual riders** use Cyclistic bikes differently, to support a marketing campaign that converts casual riders into annual members.

## Table of Contents
- [Business Task](#business-task)
- [Data Sources](#data-sources)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Analysis Summary](#analysis-summary)
- [Key Findings](#key-findings)
- [Recommendations](#recommendations)
- [Repository Structure](#repository-structure)
- [Tools Used](#tools-used)
- [Limitations](#limitations)
- [Scope](#scope)

## Business Task
Cyclistic's marketing team wants to convert casual riders (customers who buy single-ride or full-day passes) into annual members, since finance has confirmed that members are significantly more profitable.

**Question answered in this project:** How do annual members and casual riders use Cyclistic bikes differently?

## Data Sources

| Aspect | Details |
| --- | --- |
| Source | Cyclistic historical trip data, provided under Motivate International Inc.'s license |
| Time range | 12 months, Jan 2021 – Dec 2021 |
| Grain | One row per ride: start/end timestamp, start/end station, bike type, rider type (member vs. casual) |
| Volume | ~4.2 million rides across 12 monthly files |
| Privacy | No personally identifiable information; rides cannot be traced to individuals |
| Credibility (ROCCC) | Reliable, original, comprehensive, current, cited |

## Data Cleaning and Preparation
The twelve monthly files were combined and standardised into a single table:

- Added `ride_length` (`ended_at − started_at`), formatted as a duration
- Added `day_of_week` (1 = Sunday … 7 = Saturday)
- Removed rides with negative or zero `ride_length` and very short rides (under 1 minute, likely false starts)
- Standardised column names and data types across all twelve files
- Flagged and reviewed extreme outliers (e.g., rides over 24 hours, likely bikes not returned properly)

## Analysis Summary

| Metric | Annual Members | Casual Riders |
| --- | --- | --- |
| Average ride length | **15.12 min** | **28.48 min** |

Casual rides were on average **13.36 minutes longer** than member rides.

- **Day of week:** Member volume stays comparatively flat across weekdays; casual volume peaks on weekends.
- **Seasonality:** Casual ridership climbs through spring/summer and drops in winter; member ridership is relatively stable month to month.

## Key Findings
1. **Longer rides:** Casual riders take much longer trips than members, suggesting leisure use rather than point-to-point transport.
2. **Weekend concentration:** Casual ridership concentrates on weekends, while member ridership is steady across weekdays, consistent with commuting.
3. **Seasonality:** Casual ridership is far more seasonal, spiking in warm months and dropping sharply in cold ones.

## Recommendations
1. **Introduce a weekend-focused membership option** (based on Finding 2)
   A lower-commitment tier (weekend-only or reduced-price trial) for riders with a weekend-heavy pattern, converting regular riders without requiring a switch to weekday commuting.
2. **Run a weekday commuter trial promotion** (based on Finding 2)
   Target casual riders near high-traffic commute stations with a discounted trial timed to weekday usage, testing whether commute-framed messaging moves riders toward membership.
3. **Front-load membership marketing before peak season** (based on Finding 3)
   Launch conversion campaigns at the start of the high-ridership season rather than at its peak, to reach casual riders while they are actively riding.

## Repository Structure
```
├── data/               # Raw monthly trip files (Jan–Dec 2021)
├── notebooks/          # Cleaning and analysis notebooks / scripts
├── visuals/            # Charts and dashboards
├── report/
│   └── Final_report.docx
└── README.md
```
> Adjust this tree to match your actual folders.

## Tools Used
- Spreadsheets / SQL / R / Python (update with the tools you actually used)
- Data visualisation (e.g., Tableau, Power BI, ggplot2, matplotlib)

## Limitations
- No personally identifiable information, so it is not possible to confirm whether a casual rider lives in the service area or has bought multiple single passes.
- Analysis covers a single year (2021), so seasonal patterns reflect one cycle only.

## Scope
Out of scope here (handled separately by teammates): why a casual rider would choose to upgrade, and how digital media could influence that decision.

## Data License
Data is provided by Motivate International Inc. under its published license. Please review the license terms before reusing the data.

## Author
*Your name* · [LinkedIn](#) · [Portfolio](#)
