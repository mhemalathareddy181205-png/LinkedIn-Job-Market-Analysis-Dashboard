# LinkedIn Job Market Analysis Dashboard

**File:** `LinkedIn_Job_Market_Analysis.pbix`
**Tool:** Microsoft Power BI

## Overview

This Power BI report analyzes LinkedIn job posting data to surface hiring trends across skills, companies, locations, work types, experience levels, and compensation. The dashboard is built as a single-page, KPI-driven report with interactive slicers for on-the-fly filtering.

## Data Model

The report is built on a star-schema style model with the following tables:

| Table | Role | Key fields used in report |
|---|---|---|
| `Fact_JobPostings` | Fact table of individual job postings | `formatted_work_type`, `formatted_experience_level` |
| `Bridge_JobSkills` | Bridge table linking jobs to skills; hosts core measures | `job_id`, `Total Jobs`, `Total Companies`, `Total Locations`, `Average Salary` |
| `Dim_Skills` | Skill dimension | `skill_name` |
| `Dim_Company` | Company dimension | `company_name` |
| `Dim_Location` | Location dimension | `location` |

### Key Measures
- **Total Jobs** – count of job postings
- **Total Companies** – count of distinct hiring companies
- **Total Locations** – count of distinct job locations
- **Average Salary** – average posted salary across jobs

## Dashboard Layout (Page 1)

**Title:** "LinkedIn Job Market Analysis"

### KPI Summary Card
A top strip displaying four headline metrics: **Total Jobs, Total Companies, Total Locations,** and **Average Salary**.

### Visuals

| # | Visual Type | Title | Purpose |
|---|---|---|---|
| 1 | Clustered Bar Chart | Top 5 in-demand skills | Ranks skills by number of job postings requiring them |
| 2 | Donut Chart | Work type distribution | Breaks down postings by employment type (e.g., full-time, contract) |
| 3 | Treemap | Jobs by experience level | Shows job volume by seniority level |
| 4 | Clustered Bar Chart | Top hiring companies | Ranks companies by number of postings |
| 5 | Column Chart | Avg. salary by experience level | Compares average salary across seniority tiers |
| 6 | Pivot Table | Top 10 locations | Lists locations with the highest job counts |

### Interactive Slicers
- **Location** – filter by job location
- **Work Type** – filter by employment type
- **Experience Level** – filter by seniority level

### Key Insight (callout panel)
> Entry-level and Mid-Senior roles dominate hiring (54% combined), while Associate and Director tiers are roughly 5x thinner — signaling a mid-career pipeline gap employers should watch.

### Branding / Visual Elements
The report includes a LinkedIn logo, decorative background imagery (office building visuals, map graphic, user icon), and a themed color palette (custom theme + built-in "Tidal" theme resources bundled in the file).

## How to Use
1. Open `FINAL_PROJECT_LINKEDIN.pbix` in Power BI Desktop (or Power BI Service if published).
2. Use the **Location**, **Work Type**, and **Experience Level** slicers at the top to filter the entire page.
3. Hover over any chart for tooltips with exact values.
4. The KPI card at the top updates dynamically based on active slicer selections.

## Requirements
- Power BI Desktop (recent version recommended for full visual compatibility)
- No external data connections detected outside the embedded data model (data is stored in-file)

## Notes for Future Development
- Currently a single-page report; could be expanded with additional pages (e.g., trend-over-time analysis, geographic map view, salary distribution by skill).
- Consider adding a data dictionary tab or documentation page directly inside the .pbix for end users.
