# Pharma Promotion ROI, data dictionary

The model loads from `pharma_sales_promo_data.xlsx`, with one calculated date dimension and one synthetic benchmark built inside the model. All field names below match the model.

## Sales, fact

| Column | Type | Description |
|---|---|---|
| `SaleID` | text | Unique sale identifier. |
| `Date` | date | Sale date. Stored in the workbook as an Excel serial number, converted to a real date in Power Query. |
| `PhysicianID` | text | Prescribing physician, joins `Physicians`. |
| `ProductID` | text | Product sold, joins `Products`. |
| `Units` | whole number | Units sold. |
| `Revenue` | decimal | Sales revenue. |
| `SalesRepID` | text | Sales representative identifier. |

## Promo_Activities, fact

| Column | Type | Description |
|---|---|---|
| `ActivityID` | text | Unique promotion activity identifier. |
| `Date` | date | Activity date. Stored in the workbook as an Excel serial number, converted to a real date in Power Query. |
| `PhysicianID` | text | Targeted physician, joins `Physicians`. |
| `ChannelID` | text | Promotion channel, joins `Promo_Channels`. |
| `Cost` | decimal | Activity cost. |
| `Reach` | whole number | Physicians reached by the activity. |
| `AttributedRevenue` | decimal | Revenue attributed to the activity by the attribution model. |
| `ROI_pct` | decimal | Source provided return percentage for the activity. |

## Physicians, dimension

| Column | Type | Description |
|---|---|---|
| `PhysicianID` | text | Physician key. |
| `Name` | text | Physician name. |
| `Specialty` | text | Clinical specialty. |
| `TerritoryID` | text | Sales territory identifier. |
| `Region` | text | Geographic region. |
| `Decile` | whole number | Prescriber decile, 1 to 10. |
| `Segment` | text | Value segment, High Value, Mid Value, or Low Value. |

## Products, dimension

| Column | Type | Description |
|---|---|---|
| `ProductID` | text | Product key. |
| `ProductName` | text | Product name. |
| `TherapeuticArea` | text | Therapeutic area. |
| `UnitPrice` | whole number | List price per unit. |

## Promo_Channels, dimension

| Column | Type | Description |
|---|---|---|
| `ChannelID` | text | Channel key. |
| `ChannelName` | text | Channel name. |
| `ChannelType` | text | `Personal` or `Non-Personal`. |
| `AvgCostPerContact` | whole number | Average cost per contact for the channel. |

## Calendar, date dimension

A calculated date table spanning `2025-06-01` to `2026-05-31`, marked as the model date table. Columns are `Date`, `Year`, `Month`, `MonthName`, `Quarter`, `YearMonth`.

## Market_Benchmark, SYNTHETIC benchmark

This table is not real market data. It is generated inside the model as a calculated table, so that share of voice has a market denominator. The grain is one row per channel per month start date. `MarketReach` is seeded deterministically from the channel and the month, so brand reach lands at roughly 15 to 30 percent of market, varying by channel and by month, and the result is reproducible on every refresh. Treat it as an illustrative competitive baseline, never as a real audited market figure.

| Column | Type | Description |
|---|---|---|
| `ChannelID` | text | Promotion channel, joins `Promo_Channels`. |
| `Date` | date | Month start date, joins `Calendar`. |
| `MarketReach` | decimal | Synthetic total market reach for the channel and month. |
