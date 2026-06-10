# UK RAILWAY STATION OPERATIONS & PERFORMANCE ANALYSIS
---

# Table of Contents
---
- [Analysis Overview](#analysis-overview)
- [Objectives](#objectives)
- [Data Source](#data-source)
- [Dataset Overview](#dataset-overview)
- [Tools Used](#tools-used)
- [Data Cleaning & Preparation](#data-cleaning--preparation)
- [Skills Demonstrated](#skills-demonstrated)
- [KPI Overview](#kpi-overview)
- [Insights](#insights)
- [Recommendations](#recommendations)
- [Dashboard](#dashboard)
- [Conclusion](#conclusion)

---

## Analysis Overview
---
Across 9 major UK railway stations, journeys were
being delayed and cancelled but operations teams
had no clear picture of where delays were
concentrated, when they were most likely to happen,
or what was actually causing them.

This project analyses 31,653 passenger journey
records from January to April 2024 to answer one
central question: are railway delays random system
failures, or are they predictable and preventable?

The answer is clear they are predictable.
And that changes everything about how to fix them.

---

## Objectives
---

- Identify the stations with the highest delays and the main causes behind them.
- Compare delay causes and refund rates across **Advance, Anytime, and Off-Peak** ticket types.
- Discover when delays are most likely to occur based on the **day of the week** and **hour of the day**.
- Provide practical, data-driven recommendations that station managers can use to improve railway operations.

---

## Data Source
---

- **Source:** UK National Rail transaction records
- **Period:** January 2024 – April 2024
- **Dataset Size:** 31,653 passenger journey records
- **Stations Covered:** 9 major UK railway stations
- **Ticket Types:** Advance, Anytime, and Off-Peak
- **Journey Status:** On Time, Delayed, and Cancelled
- **Ticket Class:** Standard and First Class
- **Delay Cause Categories:** 7 categories, including Signal Failure, Weather, Technical Issues, Staff Shortage, and more

![Raw dataset — attach your image here](images/railway_raw_data.png)

---

## Dataset Overview
---

| Dimension | Detail |
|-----------|--------|
| Total Records | 31,653 |
| Departure Stations | 9 major UK stations |
| Ticket Types | Advance, Anytime, Off-Peak |
| Ticket Classes | Standard, First Class |
| Journey Statuses | On Time, Delayed, Cancelled |
| Delay Cause Categories | 7 categories |
| Data Period | January – April 2024 |

---

## Tools Used
---

- **Microsoft Excel:** Used for data cleaning, creating calculated columns, and building the interactive dashboard, including KPI cards, charts, slicers, and visualizations.

- **Excel Data Model:** Used to create calculated columns such as delay minutes, delay flag, refund flag, year, month, day of the week, and departure hour to support analysis.

- **DAX:** Used to create custom measures, including Average Delay, Refund Rate, Cancellation Rate, and Percentage of Delayed Journeys.

 ### Key DAX Measures Used
---

The following DAX measures were created to support the dashboard analysis.


![Average Delay Measure](images/dax_average_delay.png)

![Refund Rate Measure](images/dax_refund_rate.png)

![Cancellation Rate Measure](images/dax_cancellation_rate.png)

![% Delayed Measure](images/dax_percentage_delayed.png)
![DAX Measures](images/railway_dax_measures.png)

---

## Data Cleaning & Preparation
---

Before the analysis, the dataset was cleaned and prepared in Microsoft Excel to ensure accurate calculations and reliable insights.

### Step 1 — Handled Missing Values

Blank values in the **Reason for Delay** and **Railcard** columns were replaced with **"None."**

For cancelled journeys, missing delay values were filled with **"N/A"** so they would not affect the average delay calculation.

---

### Step 2 — Created New Calculated Columns

Several calculated columns were created to support KPI calculations and dashboard visualizations.

- **Delay (minutes)** — Stores the delay time for each delayed journey.
- **Delay Flag** — Returns **1** for delayed journeys and **0** otherwise.
- **Refund Flag** — Returns **1** when a refund was requested and **0** otherwise.
- **Year** — Extracted from the journey date.
- **Month** — Created for monthly trend analysis.
- **Day of the Week** — Used to identify weekly patterns.
- **Hour of Departure** — Used to analyze delays by time of day.

---

### Step 3 — Standardized Data Formats

Date columns were formatted consistently, and the price column was standardized to ensure accurate calculations across the analysis.

---

### Step 4 — Applied Conditional Formatting

Conditional formatting was used to highlight journeys with delays greater than zero minutes, making delayed records easier to identify during data review.

---

After cleaning, the dataset was reviewed and prepared for dashboard development and analysis.

---

Below are screenshots showing key parts of the data preparation process:

![Missing Values](images/railway_blank_cells.png)

![Calculated Columns](images/railway_calculated_columns.png)

![Conditional Formatting](images/railway_conditional_formatting.png)

---

## Skills Demonstrated
---

- Data cleaning and data preparation in Excel  
- Handling missing values and data quality checks  
- Calculated column creation for analytics and KPI development  
- DAX measure development for business metrics  
- Pivot table analysis and data aggregation  
- Interactive dashboard design using slicers and filters  
- Time-series analysis (daily, monthly, and hourly trends)  
- Segmentation analysis (by station, ticket type, and class)  
- Root cause analysis of operational delays  
- Data storytelling and business insight communication  
---

## KPI Overview
---

| Metric | Value |
|--------|-------|
| Total Journey Records | 31,653 |
| Period Covered | Jan – Apr 2024 |
| Average Delay | 42.21 minutes |
| % Journeys Delayed | 7% |
| Cancellation Rate | 6% |
| Refund Request Rate | 4% |
| Highest Delay Station | Manchester Piccadilly (60 min avg) |
| Lowest Delay Station | Edinburgh Waverley (15 min avg) |
| Off-Peak Refund Rate | 4.22% (highest by ticket type) |
| Advance Refund Rate | 3.48% |
| Anytime Refund Rate | 2.58% |
| #1 Delay Cause | Signal Failure (all stations) |

---

## Insights
---

### Insight 1 — Station delays are concentrated, not spread evenly across the network

Manchester Piccadilly averages 60 minutes of delay
and London Euston averages 54 minutes, pulling
the network-wide average to 42 minutes. Edinburgh
Waverley sits at the other end with just 15 minutes.
Signal failure is the number one delay cause at
every single station without exception, confirming
this is an infrastructure problem, not a management
one.

![Average delay by station — attach your image here](images/railway1.png)

**Key Takeaway:**
Delays are concentrated at specific busy stations.
Fixing signal infrastructure at the top 7 stations
addresses the majority of total network delay
minutes.

---

### Insight 2 — Delays peak on Wednesdays at 8–9 AM — driven by demand, not system failure

Wednesday records the highest delays of the week
followed by Tuesday and Thursday. This pattern
aligns exactly with peak journey volume on those
days not with any increase in system faults.
The 8–9 AM delay spike matches commuter rush hour
with weather compounding the effect specifically
at 8 AM. This is the most important finding in
the project: delays are predictable and manageable,
not random.

![Delays by day of week — attach your image here](images/railway2.png)

![Delays by hour of day — attach your image here](images/railway3.png)

**Key Takeaway:**
Scale staffing and monitoring specifically on
Tuesday–Thursday and during the 8–9 AM window.
Deploy proactive weather protocols using 24-hour
forecasts before morning operations begin.

---

### Insight 3 — Off-Peak passengers face the worst delays and the highest refund rate

Off-Peak ticket holders experience the longest
average delays at 49 minutes and have the highest
refund request rate at 4.22%. Despite facing the
worst service outcome they receive no automatic
compensation, they must actively request refunds
and many do not bother. This is a hidden service
failure in the data.

![Refund rate and delay by ticket type — attach your image here](images/railway4.png)

**Key Takeaway:**
Introduce automatic threshold-based refunds for
Off-Peak passengers when delays exceed 30 minutes.
This reduces complaints, rebuilds trust, and costs
less than reactive dispute handling.

---

### Insight 4 — Both Standard and First-Class passengers face identical delay causes

Both Standard and First-Class passengers face the
exact same delay causes in the exact same order,
signal failure first, weather second. There is no
meaningful difference by ticket class. This confirms
the delay problem is entirely at the infrastructure
and scheduling layer not the service level.
Solving signal failure helps every passenger
equally regardless of what they paid.

![Delay causes by ticket class — attach your image here](images/railway_ticket_class.png)

**Key Takeaway:**
Roll out real-time SMS and app delay alerts
uniformly to all passengers regardless of ticket
class. The information gap between classes should
close, not widen.

---

### Insight 5 — Birmingham New Street has a specific technical failure pattern

While signal failure dominates across the network
Birmingham New Street shows a distinct pattern of
equipment-related technical failures that require
a station-specific response, separate from the
wider signal upgrade programme.

![Birmingham New Street delay causes — attach your image here](images/railway_birmingham.png)

**Key Takeaway:**
Deploy a dedicated quick-response maintenance team
at Birmingham New Street to resolve equipment
failures fast, this station needs a different
solution from the rest of the network.

---

## Recommendations
---

**Infrastructure**
- Prioritise signal system upgrades at Manchester
  Piccadilly, London Euston, King's Cross, York,
  Liverpool, Paddington and Reading, these 7
  stations account for the majority of network
  delay minutes

**Station-Specific**
- Deploy a quick-response maintenance team at
  Birmingham New Street for equipment failure
  response, this station requires a separate
  technical solution

**Staffing & Scheduling**
- Scale staffing on Tuesday–Thursday and during
  the 8–9 AM window to match actual passenger
  demand patterns
- Reduce overcrowding at the five highest-traffic
  stations through improved scheduling and
  passenger flow management

**Passenger Experience**
- Introduce automatic refunds for Off-Peak
  passengers when delays exceed 30 minutes
- Roll out uniform real-time SMS and app delay
  alerts to all passengers regardless of ticket
  class

**Weather Response**
- Use 24-hour forecasts to pre-alert passengers,
  deploy backup transport options and inspect
  tracks before morning peak operations begin
  — weather compounds delays specifically at 8 AM

---

## Dashboard
---
One interactive dashboard was built in Excel
covering all key performance areas — KPI cards,
average delay by station, delay causes by ticket
type, refund rates, delays by day and hour, and
slicers for filtering by station, ticket type
and month.

![Dashboard — UK Railway Operations and Performance](images/railway-dashboard.png)

---

## Conclusion
---
This analysis of 31,653 UK railway journey records
proves that delays are not random but they are
concentrated, demand-driven and fixable.

Signal failure is the dominant root cause across
all 9 stations. Manchester Piccadilly and London
Euston pull the entire network average up. Delays
peak predictably on Wednesdays at 8–9 AM driven
by passenger volume, not system breakdown. Off-Peak
passengers carry the heaviest delay burden and
receive the least compensation. And Birmingham
New Street has a distinct technical issue that
requires its own targeted solution.

All seven recommendations are evidence-backed,
specific and actionable by operations teams
without waiting for a major budget cycle.

The path forward is clear. The data has already
shown the way.

---

Thank you for reading!

Let's connect:

[LinkedIn](https://www.linkedin.com/in/peace-ada-95b341341)
[Portfolio](https://peace-ada.github.io/Data-Portfolio/)
[Email](mailto:peaceada100@gmail.com)
