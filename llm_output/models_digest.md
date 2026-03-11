# Experian Regional Econometric Model (REM) / Regional Planning Service (RPS)

Claude Code compiled doc.

## Overview

Experian's Regional Planning Service (RPS) — also referred to as the Regional Econometric Model (REM) or Regional Planning Model (RPM) — is a **top-down econometric forecasting system** used extensively in UK planning for employment land reviews, housing needs assessments, and Strategic Economic Plans (SEPs). It provides economic data and forecasts for the UK, its 12 regions, over 70 counties and 380+ local authorities.

Consultancies such as [Lichfields](https://lichfields.uk/) commonly use Experian REM baseline forecasts as the starting point for local authority employment and housing projections (e.g. the "REM 2019" line in SEP growth charts comparing underlying vs aspirational growth scenarios).

## Model Structure: Four-Layer Top-Down Architecture

The model operates as a hierarchy of four linked components, each feeding down to the next:

### 1. Macro Model (UK-level)

Experian uses a **heavily customised version of NIGEM** (the National Institute Global Econometric Model, maintained by [NIESR](https://niesr.ac.uk/nigem-macroeconomic-model)) to produce core UK macroeconomic forecasts. NIGEM is a general equilibrium model of the UK and world economy that forecasts aggregate GVA, expenditure, income and employment based on the UK National Accounts. The UK variables from NIGEM are treated as **exogenous** (imposed from above) for all subsequent layers.

### 2. Sectoral Model

An **Input-Output based model** disaggregates the core NIGEM macro forecast into industries and sub-sectors. This model:

- Converts aggregate demand into intermediate and final value added for each sector using **Input-Output Use Tables**
- Is iterative and captures intra-industry relationships
- Produces **industry-level GVA** forecasts
- Uses industry GVA together with **wage forecasts** to derive employment by sector

### 3. Regional Model

The regional layer distributes national sectoral forecasts across the 12 UK regions. Key features:

- **Workplace-based employment** drives aggregate hours worked, wages and GVA at the regional level
- Each industry's regional forecast is produced by forecasting **shares of the region within the UK industry**
- The most timely data source is the **ONS workforce jobs series** (quarterly), with employee jobs, self-employed jobs and government trainees published at SIC 2007 Section level (22 sectors)

### 4. Local Model (Local Authority level)

The local disaggregation works as follows:

- The starting point is an estimate of **growth in the participation rate** of those aged 16-64 and 65+ in a local area, used to derive labour force growth
- **Demand for labour** is estimated at the industry level by linking job growth in a local area to growth in the same industry at the regional level
- Data at the local level is more likely to be incomplete or inconsistent than at regional level, requiring greater application of techniques to construct missing data and remove inconsistencies

## Sector Classification

Experian uses a **bespoke 38-sector classification** constructed by disaggregating the SIC 2007 Section-level data (22 sectors) to 2-digit SIC level and then reaggregating. This provides more granular industry detail than the standard SIC Sections while remaining manageable for local-level forecasting.

## Data Sources

All economic history used in the RPS is derived from **official statistics published by the ONS**:

- **Workforce Jobs Series** (quarterly) — the primary employment data source at regional level
- **Business Register and Employment Survey (BRES)** — for local authority level employment
- **ONS National Accounts** — for GVA, expenditure and income aggregates
- **Sub-National Population Projections** — for demographic inputs

Experian uses existing statistics in the form they are published to the greatest extent possible.

## Key Variables Forecast

| Variable | Geographic levels |
|---|---|
| GVA by industry | UK, Region, County, Local Authority |
| Employment by sector (38 sectors) | UK, Region, County, Local Authority |
| Wages | UK, Region |
| Labour market (participation, unemployment) | UK, Region, Local Authority |
| Demographics / Population | UK, Region, Local Authority |
| Household income and spending | UK, Region, Local Authority |

## How It Is Used in Planning

The Experian REM/RPS is one of three main econometric forecast providers used in UK local planning (alongside [Cambridge Econometrics / LEFM](https://www.camecon.com/how/lefm-model/) and Oxford Economics). Its forecasts are used as:

- **Baseline employment projections** in Employment Land Reviews
- **Labour demand inputs** to Objectively Assessed Housing Need (OAN) calculations
- **Scenario baselines** in Strategic Economic Plans — e.g. comparing "underlying growth" (baseline trend) against "aspirational growth" scenarios that layer in additional policy-driven employment

The "REM 2019" vintage referenced in SEP charts (such as the Lichfields analysis comparing SEP underlying growth vs aspirational growth vs REM forecasts) represents the specific forecast run from 2019, which would have incorporated data and assumptions current at that time.

## Comparison with Other UK Regional Models

| Model | Provider | Approach |
|---|---|---|
| **Experian REM/RPS** | Experian | Top-down from customised NIGEM; I-O sectoral model; 38 sectors |
| **LEFM** | Cambridge Econometrics | Based on MDM-E3; Keynesian structure with I-O system; 46 regional sectors |
| **Oxford Economics** | Oxford Economics | Global macro model with regional disaggregation |
| **Working Futures** | IER / Cambridge Econometrics | Uses MDM-E3 (87 UK sectors, 46 regional); 5,000+ behavioural relationships |

## Sources

- [Experian Guide to RPM (via Burnley Council)](https://burnley.gov.uk/wp-content/uploads/2022/02/41659-Appendix-5-Experian-Guide-to-RPM-191115.pdf) — the primary methodology document
- [Experian Regional Economic Forecasts](http://www.experian.co.uk/economics/economic-forecasts/regional-economic-forecast.html)
- [Experian UK Local Level Economic Forecasting (Digital Marketplace)](https://www.applytosupply.digitalmarketplace.service.gov.uk/g-cloud/services/283208369834515)
- [NIESR — NiGEM Macroeconomic Model](https://niesr.ac.uk/nigem-macroeconomic-model)
- [Working Futures 2017-2027 Technical Report (GOV.UK)](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/863508/Working_Futures_Technical_Report.pdf)
- [Cambridge Econometrics — LEFM](https://www.camecon.com/how/lefm-model/)
- [East of England Forecasting Model Technical Report](https://cambridgeshireinsight.org.uk/wp-content/uploads/2020/07/EEFM_2017_technical_report_June2018.pdf)
