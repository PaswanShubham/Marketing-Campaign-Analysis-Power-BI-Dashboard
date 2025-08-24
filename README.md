# Marketing Campaign Analysis — Power BI Dashboard

<img src="dashboard.png" alt="Marketing Campaign Analysis Dashboard preview" width="900">

## Overview
End-to-end Power BI dashboard to evaluate digital marketing performance across channels and time. It tracks spend efficiency and funnel health, and helps teams compare categories with interactive slicers.

## Metrics (with definitions)
- **Ad Spend** — Total marketing spend.
- **Clicks** — Number of ad clicks.
- **Click-Through Rate (CTR %)** — Clicks / Impressions.
- **Conversions** — Count of desired actions (e.g., purchases, sign-ups).
- **Conversion Rate (CVR %)** — Conversions / Clicks.
- **Impressions** — Ad views.
- **Cost per 1000 Impressions (CPM)** — (Ad Spend / Impressions) × 1000.

## Visuals
- **Area Chart** — Trends for **Spend** and **Conversions** over time (ROI signals).
- **Line & Stacked Column** — Monthly **Revenue** (columns) vs **Ad Spend** (line) to see spend-to-revenue relationship.
- **Donut Chart** — **Spend distribution** by Channel.
- **Clustered Bar** — **Impressions vs Clicks** per month.
- **Slicer(s)** — Interactively compare **Channel / Campaign / Category**.

## How to Use
1. Open `pbix/MarketingCampaignAnalysis.pbix` in **Power BI Desktop**.
2. Filter by **Channel / Category** slicers and adjust date range.
3. Hover for tooltips; compare CTR/CVR/CPM across segments.

## DAX Measure Examples
> Adjust column/table names if yours differ (e.g., `FactAds[Spend]`).

```DAX
Ad Spend = SUM(FactAds[Spend])
Clicks   = SUM(FactAds[Clicks])
Impressions = SUM(FactAds[Impressions])
Conversions = SUM(FactAds[Conversions])
Revenue = SUM(FactAds[Revenue])  -- optional if available

CTR % = DIVIDE([Clicks], [Impressions])
Conversion Rate % = DIVIDE([Conversions], [Clicks])
CPM = DIVIDE([Ad Spend], [Impressions]) * 1000
CPC = DIVIDE([Ad Spend], [Clicks])
CPA = DIVIDE([Ad Spend], [Conversions])
ROAS = DIVIDE([Revenue], [Ad Spend])
