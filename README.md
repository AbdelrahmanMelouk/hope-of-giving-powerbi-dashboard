# Hope of Giving | Orphan Care Dashboard

## Overview

This Power BI project was developed for an Orphan Care Organization to provide a comprehensive view of both financial performance and social impact.

The dashboard transforms operational and financial records into actionable insights that support management decision-making, budget monitoring, spending analysis, and beneficiary tracking.

---

## Project Objectives

The dashboard helps answer key business questions:

- How much budget has been allocated and spent?
- What is the current remaining balance?
- Which support categories consume the largest share of the budget?
- How does spending evolve over time?
- How many orphans are currently supported?
- How has the number of supported orphans changed over the years?
- How many sponsors support the organization?
- What is the distribution of sponsors by nationality?

---

# Dashboard Pages

## 1. Executive Overview

Designed for management and decision-makers to monitor the organization's overall performance.

### Key KPIs

- Total Budget
- Actual Spending
- Remaining Balance
- Budget Utilization %
- Total Number of Orphans

### Visualizations

- Budget vs Actual Spending by Category
- Spending Distribution by Category
- Monthly Spending Trend
- Orphan Growth Trend
- Sponsors Distribution by Nationality

---

## 2. Sponsors & Beneficiaries

Focused on beneficiaries and sponsor-related insights.

### Key KPIs

- Total Sponsors
- Total Supported Orphans
- Sponsor Growth
- Orphan Growth
- Nationality Distribution

### Visualizations

- Sponsors Trend Over Time
- Orphan Trend Over Time
- Sponsors by Nationality
- Beneficiaries Analysis
- Financial Contribution Analysis

---

# Data Preparation & Modeling

The original dataset was provided in multiple separated operational sheets representing different spending categories.

### Original Categories

- Education
- Medical Support
- Clothing
- Food Support
- Books
- Other Expenses

### Data Transformation Process

- Cleaned and standardized the source data.
- Restructured multiple tables into a unified analytical model.
- Appended all spending categories into a single fact table.
- Created a dedicated Category field.
- Built custom relationships and reporting structure.
- Developed reusable DAX measures for business calculations.

---

# Key Metrics

### Budget Utilization %

```DAX
Budget Utilization % =
DIVIDE(
    [Actual Spending],
    [Total Budget]
)
```

### Remaining Balance

```DAX
Remaining Balance =
[Total Budget] - [Actual Spending]
```

### Total Orphans

```DAX
Total Orphans =
MAX(Fact_Expenses[Number Of Orphans])
```

### Active Categories

```DAX
Active Categories =
CALCULATE(
    DISTINCTCOUNT(Fact_Expenses[Category]),
    Fact_Expenses[Actual Spending] > 0
)
```

---

# Technologies Used
<img width="1203" height="680" alt="image" src="https://github.com/user-attachments/assets/f0e65328-7600-4881-b78f-9ee35c137262" />

    <img width="1208" height="675" alt="image" src="https://github.com/user-attachments/assets/10ee1974-4e48-44a7-bcef-4d7b31763f67" />


- Power BI Desktop
- Power Query
