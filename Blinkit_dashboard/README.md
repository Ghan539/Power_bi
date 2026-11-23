# BlinkIT Grocery Sales Analysis Dashboard

An interactive **Power BI dashboard** designed to explore BlinkIT grocery sales performance across product categories, outlet characteristics, and store locations. The report brings key performance indicators and supporting visualizations together to help users examine sales trends and compare outlet segments.

> **Project type:** Business Intelligence / Data Analytics  
> **Tool:** Microsoft Power BI  
> **Dataset table identified in the report:** `BlinkIT Grocery Data`  
> **Report pages:** 1

---

## Table of Contents

- [Project Overview](#project-overview)
- [Business Objectives](#business-objectives)
- [Key Performance Indicators](#key-performance-indicators)
- [Dashboard Features and Visualizations](#dashboard-features-and-visualizations)
- [Interactive Filters](#interactive-filters)
- [Data Model and Fields](#data-model-and-fields)
- [Metric Selection](#metric-selection)
- [Tools and Technologies](#tools-and-technologies)
- [Repository Structure](#repository-structure)
- [How to Use the Dashboard](#how-to-use-the-dashboard)
- [Analytical Questions](#analytical-questions)
- [Notes and Limitations](#notes-and-limitations)
- [Future Enhancements](#future-enhancements)

---

## Project Overview

The BlinkIT Grocery Sales Analysis Dashboard provides a consolidated view of grocery sales data. It is designed to make it easier to explore performance through different dimensions, including:

- Item type
- Item fat content
- Outlet location type
- Outlet size
- Outlet type
- Outlet establishment year

The report combines KPI cards, charts, a funnel, and a summary table. Interactive slicers allow users to narrow the analysis to selected outlet locations, outlet sizes, and item categories.

The dashboard is intended for exploratory business analysis and for practicing data visualization, KPI reporting, and interactive dashboard development in Power BI.

## Business Objectives

The dashboard supports the following analysis objectives:

1. Monitor overall sales performance using summary KPIs.
2. Compare sales across grocery item categories.
3. Examine the contribution of different fat-content groups.
4. Compare fat-content sales across outlet location types.
5. Explore sales by outlet establishment year.
6. Understand how sales are distributed across outlet sizes and outlet location types.
7. Compare outlet types using a consolidated performance table.
8. Allow users to investigate the report interactively using slicers and metric selection.

## Key Performance Indicators

The report contains four KPI measures from the `BlinkIT Grocery Data` table.

| KPI | Measure name in Power BI | Purpose |
|---|---|---|
| Total Sales | `Total_Sales` | Summarizes sales value for the current filter context. |
| Average Sales | `Avg_Sales` | Shows the average sales value according to the measure definition. |
| Number of Items | `No Of Items` | Displays the item count according to the measure definition. |
| Average Rating | `Avg Rating` | Shows the average rating according to the measure definition. |

**Important:** KPI values change when applicable report filters or visual selections are applied. The exact calculation logic depends on the DAX definitions stored in the Power BI model.

## Dashboard Features and Visualizations

The uploaded PBIX contains one report page with the following visual types and analytical views.

| Visualization | Analysis |
|---|---|
| KPI Cards | Displays Total Sales, Average Sales, Number of Items, and Average Rating. |
| Bar Chart – Item Type | Compares the selected sales metric across item categories. |
| Donut Chart – Fat Content | Shows the selected metric split by item fat content. |
| Clustered Bar Chart – Fat By Outlet | Compares fat-content groups across outlet location types. |
| Line Chart – Outlet Establishment Year | Plots the sum of Sales against outlet establishment year. |
| Donut Chart – Outlet Size | Shows the selected metric distribution across outlet size groups. |
| Funnel – Outlet Location Type | Compares the selected metric across outlet location types. |
| Summary Table – Outlet Type | Presents sales, item count, average sales, average rating, and item visibility by outlet type. |

### How to interpret the visuals

- **Item Type:** Identify which product categories contribute more or less to the selected metric.
- **Fat Content:** Compare the contribution of different fat-content categories.
- **Fat By Outlet:** See how fat-content categories compare across outlet location types.
- **Outlet Establishment Year:** Examine sales values across establishment-year groups. This visual uses the `Sales` column with aggregation in the chart.
- **Outlet Size:** Compare the selected metric across outlet-size categories.
- **Outlet Location Type:** Review the relative values for the available location groups.
- **Outlet Type table:** Compare multiple performance measures side by side for each outlet type.

## Interactive Filters

The report includes slicers for the following fields:

| Slicer | Field |
|---|---|
| Outlet Location Type | `Outlet Location Type` |
| Outlet Size | `Outlet Size` |
| Item Type | `Item Type` |

### Using the filters

1. Select a value in a slicer to filter the report.
2. Select multiple values if the slicer configuration permits it.
3. Observe how the KPI cards, charts, and table respond.
4. Clear the selection to return to a broader view.

The report also defines visual interactions so selections in charts can filter other visuals. The exact interaction behavior can be checked in Power BI Desktop through **Format → Edit interactions**.

## Data Model and Fields

The report references a primary table named `BlinkIT Grocery Data` and a separate field-parameter table named `Metrics`.

### Fields used in report visuals

| Field | Used for |
|---|---|
| `Sales` | Sales aggregation in the establishment-year chart and sales-related calculations. |
| `Item Type` | Product-category analysis and slicer filtering. |
| `Item Fat Content` | Fat-content analysis. |
| `Outlet Location Type` | Outlet-location comparisons and filtering. |
| `Outlet Size` | Outlet-size analysis and filtering. |
| `Outlet Establishment Year` | Establishment-year analysis. |
| `Outlet Type` | Outlet-type summary table. |
| `Item Visibility` | Item visibility value in the outlet-type summary table. |

### Measures identified in the report

- `Total_Sales`
- `Avg_Sales`
- `No Of Items`
- `Avg Rating`

### Metric selector

The report uses a field parameter named `Metrics` in several charts and a KPI card. This enables the report to switch the displayed measure rather than requiring a separate chart for every metric.

The available parameter options and their exact labels should be verified in the Power BI model.

## Metric Selection

A slicer based on the `Metrics` field parameter is included in the report. Use it to change the measure displayed by visuals that are connected to this parameter.

This makes it possible to explore the same category or outlet breakdown using different measures. Not every visual necessarily uses the parameter; for example, the establishment-year line chart uses the `Sales` column directly.

## Tools and Technologies

| Tool / Technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Dashboard development and report interaction. |
| Power Query | Data preparation, if used in the project workflow. |
| DAX | KPI measures and metric calculations. |
| BlinkIT Grocery dataset | Source data represented by the report's data model. |
| GitHub | Project documentation and version control. |

*Power Query and DAX are listed as relevant Power BI capabilities; the PBIX report structure confirms the named measures and fields, but does not by itself document every transformation step or the complete DAX formulas.*

## Repository Structure

A recommended GitHub repository structure is:

```text
BlinkIT-Grocery-Sales-Dashboard/
│
├── README.md
├── Blinkit dashboard.pbix
│
├── screenshots/
│   └── dashboard-overview.png
│
└── data/
    └── README.md
```

- `README.md` — project documentation.
- `Blinkit dashboard.pbix` — Power BI report file.
- `screenshots/` — dashboard images for the GitHub project page.
- `data/README.md` — dataset source, description, and usage notes. Add the original dataset here only if you are permitted to redistribute it.

You can adjust the folder and file names to match your actual repository.

## How to Use the Dashboard

### Requirements

- Windows computer
- Microsoft Power BI Desktop
- The `.pbix` project file

### Steps

1. Clone or download this GitHub repository.
2. Open `Blinkit dashboard.pbix` using Power BI Desktop.
3. Wait for the report and model to load.
4. Review the KPI cards for the current report context.
5. Use the slicers to filter by outlet location type, outlet size, or item type.
6. Change the `Metrics` selection to explore different measures in supported visuals.
7. Select chart segments or bars to cross-filter other visuals.
8. Clear selections when you want to return to the overall view.

If Power BI requests credentials or cannot refresh the data, check the source configuration in **Transform data → Data source settings**. The PBIX file's report layout does not establish the original source file path or whether the original data source is still available on another computer.

## Analytical Questions

Use the dashboard to investigate questions such as:

1. Which item types have the highest sales?
2. How does sales contribution vary by item fat content?
3. How do fat-content groups compare across outlet location types?
4. How do sales values vary by outlet establishment year?
5. How is the selected metric distributed across outlet sizes?
6. Which outlet location type has the largest value for the selected metric?
7. How do outlet types compare in total sales, average sales, item count, average rating, and item visibility?
8. Do the patterns change when the report is filtered to a particular item type or outlet segment?

These are suggested analysis questions, not conclusions. Actual findings should be added after reviewing the data and recording the corresponding values.

## Notes and Limitations

- This documentation is based on the structure inspected in the uploaded PBIX file.
- The report contains one page named `Page 1`.
- The PBIX structure identifies visual fields and measure names, but does not provide a verified description of the original dataset publisher or source URL.
- Exact DAX formulas, Power Query transformation steps, data-refresh credentials, and source-file locations should be documented separately if you want users to reproduce the complete data pipeline.
- The dashboard should not be interpreted as evidence of causal relationships.
- Do not publish private credentials, licensed source data, or confidential business information in the repository.

## Future Enhancements

Potential improvements for a future version include:

- Add a dedicated time-period analysis if a suitable date field is available.
- Add year-over-year or month-over-month comparisons if the dataset supports them.
- Add drill-through pages for item and outlet-level investigation.
- Add dynamic report titles that reflect active slicer selections.
- Add tooltip pages with additional context for each visual.
- Document the DAX formulas and Power Query steps.
- Add a dashboard screenshot and a short list of verified business findings.
- Validate KPI definitions and aggregation logic against the source data.

---

## Project Information

**Project:** BlinkIT Grocery Sales Analysis Dashboard  
**Platform:** Microsoft Power BI  
**Category:** Data Analytics | Business Intelligence | Data Visualization  
**File:** `Blinkit dashboard.pbix`

---

If you find this project useful, feel free to explore the report and use the analytical questions above to investigate the data.
