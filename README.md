# Telco Customer Churn Prediction

An end-to-end, data-driven analysis of customer churn within a telecom company, focused on customer segmentation and AI-driven retention strategies.

## Project Objectives

- Categorize and engineer key variables for more effective modeling.
- Create meaningful customer segments based on behavior and demographics.
- Calculate churn rates across different customer profiles.
- Visualize key patterns using bubble charts.
- Design an AI-based intervention story to reduce churn in high-risk segments.

## Variable Transformation & Feature Engineering

### Re-categorization of Variables

| Original Variable | Transformed |
|-------------------|-------------|
| `SeniorCitizen`   | 0 → `J` (Young), 1 → `S` (Senior) |
| `Tenure` (in months) | 0–6 → `06`, 7–12 → `12`, 12-18 → `18`, 18+ → "18+"  |
| `Contract`        | `Month-to-month` → `MM`, `One year` → `OY`, `Two year` → `TY` |

### New Feature: `Technology User`

A new binary feature, **`Tech. Prod. User`**, was created based on the usage of at least one of the following services:
- `OnlineSecurity`
- `OnlineBackup`
- `DeviceProtection`
- `TechSupport`

Customers using at least one of the above are labeled as **`TPU`**, others as **`NTPU`**.


## Customer Segmentation

Segments were created using the combination of the following 4 features:

- `SeniorCitizen` (J/S)
- `Tenure` category (06, 12, 18, 18+)
- `Contract` type (MM, OY, TY)
- `Tech. Prod. User` (TPU, NTPU)

**Segment Format Example:** `J-06-MM-TPU`


## Churn Rate Calculation

For each created segment, the churn rate was calculated by dividing the number of churned customers by the total number of customers in that segment.


## Bubble Chart Visualization

A bubble chart was created to visualize the **top 15 customer segments** with the highest number of customers, showing:

- **Segment Name**
- **Average Tenure**
- **Monthly Recurring Revenue (MRR)**
- **Churn Rate**

Bubble size represents churn rate.

## Key Takeaways

- Technology use alone is not enough to prevent churn.
- Short tenure and monthly contracts are key churn drivers.
- AI-powered interventions can significantly reduce churn in at-risk segments.

## AI-Based Retention Strategy

### High-Risk Segment Example:
**Segment:** `J-06-MM-NTPU`  
**Churn Rate:** 52%

### AI Strategy:

This segment includes **young customers**, with **mid-range tenure**, on **month-to-month contracts**, and using at least one technological product.

#### Suggested AI-Powered Interventions:

- **Predictive Modeling:** Identify likely churners using behavior data.
- **Personalized Offers:** Send customized data bundle promotions through digital channels.
- **Social Listening:** Use NLP on social media feedback to tailor messaging.
- **Automated Communication:** Chatbots for real-time engagement and satisfaction tracking.

---

## Dataset

- Source: Telco Customer Dataset
- Rows: 7,044
- Key Columns: `SeniorCitizen`, `Tenure`, `Contract`, `Churn`, `MonthlyCharges`, `Tech. Prod. User`
