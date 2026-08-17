# Asset Leasing Portfolio Dashboard

An interactive Power BI dashboard designed to provide a high-level view of an asset leasing portfolio across regions, lease statuses and termination trends.

## Dashboard Preview

![Asset Leasing Portfolio Dashboard]
<img width="1346" height="756" alt="image" src="https://github.com/user-attachments/assets/4f15a548-adfa-40db-9402-8517924725a3" />

## Overview

This project demonstrates how Power BI can be used to transform structured asset and lease data into an interactive portfolio management dashboard.

The dashboard provides visibility into:

- Total portfolio value
- Active lease volume
- Monthly rental revenue
- Lease termination rate
- Portfolio value by region
- Lease status distribution
- Lease termination trends
- Regional lease status breakdown

## Key Metrics

| KPI | Value |
|---|---:|
| Total Portfolio Value | $143.78M |
| Active Leases | 331 |
| Total Monthly Rent | $2.10M |
| Termination Rate | 18.59% |
| Total Lease Records | 608 |

## Dashboard Features

### Portfolio KPIs
Four KPI cards provide an executive-level summary of the portfolio.

### Portfolio Value by Region
A horizontal bar chart compares portfolio value across:

- North America
- LATAM
- APAC
- Middle East
- EMEA

### Lease Portfolio by Status
A donut chart shows the distribution of:

- Active
- Expired
- Terminated

### Lease Terminations Over Time
A time-series visualization tracks termination activity by year.

### Lease Status by Region
A matrix provides a cross-sectional view of active, expired and terminated leases across regions.

### Interactive Region Filter
Users can select a region to dynamically filter the dashboard and analyze regional portfolio performance.

## Data Model

The dashboard uses two primary tables:

### Assets

Contains asset-level information including:

- Asset ID
- Asset Type
- Region
- Acquisition Date
- Acquisition Value
- Book Value

### Leases

Contains lease-level information including:

- Lease ID
- Asset ID
- Lessee
- Region
- Start Date
- End Date
- Monthly Rent
- Term Months
- Status
- Termination Date

The tables are related using:

`assets[asset_id] → leases[asset_id]`

## DAX Measures

Key measures include:

### Total Portfolio Value

```DAX
Total Portfolio Value =
SUM(assets[book_value])
