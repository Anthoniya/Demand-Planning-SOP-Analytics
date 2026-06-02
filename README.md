# Demand Planning and S&OP Analytics: NovaMart Ireland

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-green)
![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Level](https://img.shields.io/badge/Level-Entry%20Level%20Portfolio-blue)

---

## Why I Built This

Transitioning into the supply chain without direct work experience
meant I needed to show what I could actually do, not just the 
courses I had completed. So rather than waiting for a job to
Teach me, I built the kind of project I would expect to work
on as a junior demand planner.

NovaMart Ireland is the fictional FMCG company I created as the
backdrop. I designed the dataset from scratch, chose which
demand patterns to include, built and tested two different
forecasting methods, measured the results honestly, and
documented everything the way it would appear in a real S&OP
review.

Nothing here was copied from a tutorial. Every formula, every
design decision, and every insight came from working through
the problem myself.

---

## The Business Scenario

**Company:** NovaMart Ireland (fictional)  
**Sector:** FMCG, Consumer Health and Household Products  
**Regions:** Dublin, Cork, Galway  
**Time Period:** January 2023 to December 2024  
**Products:** 6 SKUs across 2 categories  

One of the first decisions I made was to give each product a
different demand personality. A project with six identical
flat demand lines would be pointless to forecast. So I
designed one product that is growing, one that is declining,
some with strong seasonal peaks and one that is stable
year-round. That variety forced the models to actually work
and made the accuracy comparison between methods meaningful.

| SKU | Category | Demand Pattern |
|-----|----------|----------------|
| VitaShield Vitamin C 500mg | Consumer Health | Strong winter peak, January and December promotions |
| NovaCold & Flu Relief 20pk | Consumer Health | Highest seasonal swing in the range, growing year on year |
| SleepEase Melatonin 60 tabs | Consumer Health | Gradually declining, needs commercial attention |
| FreshHome Antibacterial Spray | Household | Spring cleaning peak, multipack promotions in April |
| CleanMate Dishwasher Tabs 40pk | Household | Stable and predictable, pre-Christmas promotional spikes |
| EcoWash Laundry Liquid 2L | Household | Growing trend with a summer peak, June price promotion |

---

## What the Project Covers

### Stage 1: Designing the Dataset

Rather than downloading a ready-made dataset, I created a
432-row synthetic sales file covering 24 months, 6 SKUs and
3 regions. I built in specific patterns deliberately so the
later analysis would have something real to find. Seasonal
curves, a growing SKU, a declining SKU, two promotion types, 
and realistic random variation were all part of the design.

### Stage 2: Data Cleaning and Audit

Before any analysis, I ran a 7-point data quality audit
checking row counts, unique dimensions, blank values, and
negative figures. I also added calculated columns for date,
revenue, and promotional flags. The audit sheet documents
every check with a pass/fail result, so the data quality
is transparent and verifiable.

### Stage 3: Forecasting

Two methods were tested across all 216 SKU-Region-Month
combinations for 2024. The primary method was FORECAST.ETS
with 12-period seasonality detection. Alongside it, I ran
a 3-month moving average as a simpler comparison baseline.
Testing both was deliberate because you cannot claim one
method is better without something to measure it against

### Stage 4: Accuracy Measurement

Both models were scored using MAPE, Bias, and Forecast
Accuracy percentage. MAPE tells you the average size of
your errors. Bias tells you whether you are systematically
over- or under-forecasting. Using both matters because a
forecast can look accurate on MAPE while hiding a
consistent directional problem in the bias.

### Stage 5: S&OP Summary

A monthly performance report was built covering the full year
variance analysis, SKU-level breakdown, and six business
insights written in plain language. This is the sheet a
supply chain manager would actually read in a monthly
review meeting.

### Stage 6: Exception Reporting

An automated exception report flags every SKU-Region-Month
combination by category. Promo Spike, Forecast Miss,
Over-Forecast Risk and Within Tolerance. The top 10
Exceptions are ranked by error magnitude, so attention
goes to the biggest issues first.

### Stage 7: Excel Dashboard

An executive dashboard with four KPI cards, a monthly
trend chart, SKU performance bar chart, and regional donut
chart and forecast accuracy comparison. Designed so that the 
key story is visible in under 30 seconds without reading
a single table.

### Stage 8: Power BI Dashboard 

An interactive version of the same dashboard was rebuilt in
Power BI with slicers, dynamic filters, and connected
visuals. Built from scratch as a complete beginner
to Power BI.

---

## What the Numbers Actually Showed

ETS hit 99.3% overall accuracy and won on every single SKU.
But the headline number is less interesting than what sits
underneath it.

NovaCold and Flu Relief had the biggest gap between methods.
ETS reached 99.6% while the 3-month moving average only
managed 59.7%. That nearly 40-point difference comes down
to one thing. A moving average looks backward. It reacts
to demand rather than anticipating it. For a product where
sales double in winter, by the time a moving average catches
up, the peak is already passing.

CleanMate Dishwasher Tabs told the opposite story. The most
stable product in the range. The moving average got to 97.3%
accuracy, almost identical to ETS at 98.9%. When demand is
flat, there is nothing to anticipate. Simplicity works
just as well.

That contrast is the finding I found most useful. It does
not just say ETS is better. It tells you the specific
conditions where the difference matters.

### Accuracy Results by SKU

| SKU | ETS Accuracy | MA3 Accuracy |
|-----|-------------|-------------|
| VitaShield Vitamin C 500mg | 99.0% | 59.6% |
| NovaCold & Flu Relief 20pk | 99.6% | 59.7% |
| SleepEase Melatonin 60 tabs | 99.6% | 83.9% |
| FreshHome Antibacterial Spray | 99.3% | 93.6% |
| CleanMate Dishwasher Tabs 40pk | 98.9% | 97.3% |
| EcoWash Laundry Liquid 2L | 99.6% | 86.5% |
| **Overall** | **99.3%** | **80.1%** |

### Other Findings Worth Mentioning

- Total 2024 units sold: **36,089** across all SKUs and regions
- Dublin accounted for **54.9%** of volume, Cork **26.1%**
  and Galway **19.0%**
- Monthly demand swung 37% between the July low of 2,620
  units and the December peak of 3,595
- SleepEase finished at 3,640 units against a portfolio
  average of 6,490. The decline was consistent all year
  and points to a product that needs a commercial decision
  before the next planning cycle
- FreshHome Antibacterial Spray in April was the biggest
  single forecasting miss across all three regions, up to
  3.8% below forecast. Demand fell faster than expected
  Once the spring promotion ended
- 11 exceptions were flagged across 216 combinations.
  89.4% performed within tolerance

---

## How to Navigate the Workbook

Download **NovaMart_Demand_Planning.xlsx** and enable
editing when Excel prompts you.

There are 9 sheets. This is the order I would suggest:

| Sheet | What It Shows |
|-------|--------------|
| Dashboard | Start here. Four KPIs and four charts, full picture at a glance |
| S&OP_Summary | Month by month performance, variance analysis, and business insights |
| Exception_Report | Every flagged case categorized and ranked by magnitude |
| Accuracy | MAPE, Bias, and Accuracy for both methods by SKU |
| Forecasts | All 216 ETS and MA3 forecast values for 2024 |
| Forecast_Input | The clean history table that feeds the forecast models |
| Raw-Data | Original 432-row dataset with all calculated columns |
| Data_Audit | 7-point quality audit confirming the data was clean |
| Chart_Data | Supporting tables that feed the dashboard visuals |

---

## A Few Decisions Worth Explaining

**On the 2% exception threshold**

The standard range in most demand planning environments
is 10% to 15%. At 99.3% model accuracy, a 15% threshold
flags nothing. Setting it at 2% surfaces the cases that
genuinely deviated from the baseline. In a live environment,
you would set this based on your actual error distribution
and your business tolerance for stockouts versus excess stock.

**On testing two forecast methods**

Picking ETS and declaring it the best method without
testing anything else would have proved nothing. Running
a moving average alongside it gave the comparison a point
of reference. The results were more interesting than
expected because the gap between methods was not uniform
across all products. That finding is only visible if you
test both.

**On designing the dataset with difficult patterns**

Six products with identical flat demand would have produced
a near-perfect forecast and told you nothing useful. The
deliberate messiness in this dataset, a declining product,
a growing product, different promotions, different seasonal
shapes, was the whole point. Real FMCG portfolios look
like this, and learning to handle that variety was the goal.

---

## Dashboard Preview
### Excel Dashboard
![Dashboard](screenshots/dashboard.png)

### Forecast Accuracy Summary
![Accuracy Summary](screenshots/Accuracy summary.png)

### S&OP Summary
![S&OP Summary](screenshots/Sop summary.png)

### Exception Report
![Exception Report](screenshots/Exception report.png)

---

## Skills Covered in This Project

**Excel:** FORECAST.ETS, SUMIFS, AVERAGEIFS, INDEX MATCH,
SUMPRODUCT, IFERROR, conditional formatting, data validation,
dashboard design, S&OP reporting

**Power BI:** data connection from Excel, DAX measures,
interactive visuals, slicers, report formatting, and theming

**Demand Planning:** baseline forecasting, MAPE, and Bias
measurement, S&OP process, exception reporting, promotional
demand analysis

**Data Work:** synthetic dataset design, data cleaning,
audit framework, variance analysis, translating numbers
into business language

---

## About Me

Based in Ireland and transitioning into the supply chain.
This project exists because I wanted something concrete
to bring to interviews rather than a list of courses
on a CV.

Looking for junior roles in demand planning, supply chain
analysis or operations analytics, with particular interest
in pharma, medtech, or FMCG.

[www.linkedin.com/in/anthoniaikhaduwor]
