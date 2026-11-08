# 🏨 Hotel Harmony – Data Insights for Optimized Operations

### Exploratory Data Analysis (EDA) | Python | Statistical Analysis | Business Intelligence

## 📌 Project Overview

**Hotel Harmony – Data Insights for Optimized Operations** is an Exploratory Data Analysis (EDA) project focused on understanding hotel booking patterns, cancellation behaviour, customer characteristics, pricing trends and seasonal demand.

Using the Hotel Booking Demand dataset, this project applies Python-based data analysis and statistical techniques to transform raw booking records into meaningful business insights.

The primary objective is to identify patterns and relationships that can help hotel management improve cancellation management, pricing strategies, customer engagement and operational planning.

---

## 🎯 Project Objectives

- Understand hotel booking distribution and customer behaviour.
- Identify booking cancellation patterns and potential risk factors.
- Analyze seasonal booking trends.
- Examine booking lead time and stay duration.
- Compare Average Daily Rate (ADR) across hotel types and market segments.
- Investigate unusual observations and data-quality issues.
- Apply statistical tests to validate selected relationships.
- Develop actionable, data-driven business recommendations.

---

## 📂 Dataset Information

**Dataset:** Hotel Booking Demand

**Initial Dataset Size:** 119,390 rows × 32 columns

**Final Cleaned Dataset:** 87,396 rows × 34 columns

The dataset contains hotel reservation information covering two hotel categories:

- City Hotel
- Resort Hotel

### Key Dataset Attributes

| Category | Important Features |
|---|---|
| Hotel Information | hotel |
| Booking Details | lead_time, arrival_date_month |
| Guest Information | adults, children, babies, country |
| Stay Information | stays_in_weekend_nights, stays_in_week_nights |
| Pricing | adr |
| Customer Information | customer_type |
| Booking Channels | market_segment, distribution_channel |
| Deposit Information | deposit_type |
| Cancellation | is_canceled |
| Reservation Status | reservation_status |

Two additional analytical features were created:

- `total_guests`: Total adults, children and babies per booking.
- `total_nights`: Total weekend and weekday nights per booking.

A further derived feature, `lead_time_group`, was created to categorize bookings by advance reservation period.

---

## 🛠️ Tools & Technologies

| Tool / Library | Purpose |
|---|---|
| Python | Programming and analysis |
| Jupyter Notebook | Interactive development |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| SciPy | Statistical hypothesis testing |

---

## 🧹 Data Cleaning & Preparation

The initial dataset contained missing values and duplicate records.

### 1. Missing Value Treatment

| Column | Missing Values | Treatment |
|---|---:|---|
| children | 4 | Filled with 0 |
| country | 488 | Filled with 'Unknown' |
| agent | 16,340 | Filled with 0 |
| company | 112,593 | Filled with 0 |

Zero values in `agent` and `company` were used as placeholders for missing or unrecorded identifiers, not as actual agent or company IDs.

### 2. Duplicate Removal

- Initial records: 119,390
- Exact duplicate rows removed: 31,994
- Final records: 87,396

Exact duplicate rows were removed, retaining one copy of each repeated record.

**Data limitation:** The dataset does not provide a unique reservation identifier to confirm whether every exact duplicate represents a duplicate booking or a separate booking with identical recorded attributes.

### 3. Additional Data Quality Investigations

The following unusual observations were investigated:

| Observation | Records Identified | Treatment |
|---|---:|---|
| Zero-guest bookings | 166 | Retained and flagged |
| Bookings with more than 10 guests | 14 | Retained and flagged |
| Zero-night bookings | 651 | Retained and flagged |
| Negative ADR | 1 | Retained and flagged |
| ADR above 500 | 3 | Retained and flagged |

These records were not automatically removed because unusual values may represent special booking circumstances or source-data inconsistencies.

---

## 📊 Exploratory Data Analysis

The analysis was organized into five major stages.

### 1. Univariate Analysis

Examined individual variables to understand distributions, frequencies and descriptive statistics.

Key areas:
- Hotel booking distribution.
- Overall cancellation rate.
- Monthly booking trends.
- Booking lead-time distribution.
- Guest composition.
- Total guests per booking.
- Stay duration.
- Weekend versus weekday stays.
- Average Daily Rate (ADR).

### 2. Bivariate Analysis

Examined relationships between pairs of variables.

Key investigations:
- Cancellation rate by hotel type.
- Stay duration by hotel type.
- ADR by hotel type.
- ADR by market segment.
- Cancellation rate by market segment.
- Cancellation rate by deposit type.
- Cancellation rate by lead-time group.
- Cancellation rate by customer type.

### 3. Multivariate Analysis

Investigated combinations of multiple variables to identify more detailed business patterns.

Key investigations:
- Cancellation rate by hotel type and lead-time group.
- Cancellation rate by customer type and deposit type.
- ADR by hotel type and market segment.

### 4. Statistical Analysis

Applied statistical methods to examine selected relationships.

**Chi-Square Test of Independence**

Examined the association between hotel type and cancellation status.

**Point-Biserial Correlation**

Examined the relationship between booking lead time and cancellation status.

### 5. Business Insights & Recommendations

Translated the analytical findings into practical recommendations for hotel management.

---

## 🔍 Key Business Insights

### 1. Booking Cancellation Patterns

- Overall cancellation rate: **27.49%**
- City Hotel cancellation rate: **30.04%**
- Resort Hotel cancellation rate: **23.48%**
- Transient customer cancellation rate: **30.11%**
- Group customer cancellation rate: **9.93%**

City Hotels recorded a higher cancellation rate than Resort Hotels.

### 2. Lead-Time Impact

Cancellation rates generally increased with booking lead time.

| Lead-Time Group | Cancellation Rate |
|---|---:|
| 0–7 Days | 8.43% |
| 8–30 Days | 25.37% |
| 31–90 Days | 32.01% |
| 91–180 Days | 34.98% |
| 181–365 Days | 39.68% |
| Above 365 Days | 40.88% |

Bookings made further in advance showed higher observed cancellation rates.

### 3. Customer and Deposit Behaviour

- Non Refund bookings recorded a cancellation rate of **94.70%**.
- Transient customers recorded the highest cancellation rate among customer types.
- Cancellation behaviour varied across customer and deposit categories.

The unusually high cancellation rate for Non Refund bookings requires further investigation.

### 4. Seasonal Booking Trends

| Month | Booking Count |
|---|---:|
| January | 4,693 |
| February | 6,098 |
| March | 7,513 |
| April | 7,908 |
| May | 8,355 |
| June | 7,765 |
| July | 10,057 |
| August | 11,257 |
| September | 6,690 |
| October | 6,934 |
| November | 4,995 |
| December | 5,131 |

August recorded the highest booking volume, while January recorded the lowest.

### 5. Pricing and Market Segments

| Hotel Type | Average ADR | Median ADR |
|---|---:|---:|
| City Hotel | 110.99 | 105.30 |
| Resort Hotel | 99.03 | 79.50 |

Online TA and Direct booking segments recorded comparatively higher average ADRs than Corporate and Group segments.

### 6. Guest and Stay Patterns

- Average guests per booking: **2.03**
- Median guests per booking: **2**
- Average stay duration: **3.63 nights**
- City Hotel average stay: **3.15 nights**
- Resort Hotel average stay: **4.39 nights**

Resort Hotel bookings showed longer average stay durations.

---

## 📐 Statistical Findings

### 1. Chi-Square Test of Independence

**Objective:** Examine whether hotel type and booking cancellation status are statistically associated.

| Metric | Result |
|---|---:|
| Chi-Square Statistic | 447.66 |
| Degrees of Freedom | 1 |
| P-Value | 2.33 × 10⁻⁹⁹ |
| Significance Level | 0.05 |

**Decision:** Reject the null hypothesis.

**Conclusion:** The results indicate a statistically significant association between hotel type and cancellation status.

City Hotels recorded a higher cancellation rate (30.04%) than Resort Hotels (23.48%).

### 2. Point-Biserial Correlation

**Objective:** Examine the relationship between booking lead time and cancellation status.

| Metric | Result |
|---|---:|
| Correlation Coefficient (r) | 0.1848 |
| P-Value | Below 0.05 |
| Significance Level | 0.05 |

**Conclusion:** The analysis identified a weak positive association between lead time and cancellation status.

Longer booking lead times were associated with a greater likelihood of cancellation, although lead time alone has limited explanatory strength.

---

## 💡 Business Recommendations

Based on the analysis, the following recommendations were developed:

**1. Strengthen Cancellation Management**

Monitor cancellation rates regularly, particularly for City Hotels, and introduce appropriate booking confirmation and customer engagement procedures.

**2. Monitor Long-Lead-Time Reservations**

Use periodic confirmations, pre-arrival communication and targeted reminders to monitor reservations made significantly in advance.

**3. Develop Customer-Type-Specific Strategies**

Pay particular attention to transient bookings while maintaining suitable engagement strategies for corporate and group customers.

**4. Review Deposit Policies**

Investigate the unusually high cancellation rate among Non Refund bookings before making changes to deposit policies or booking conditions.

**5. Improve Seasonal Resource Planning**

Align staffing, procurement and operational resources with seasonal booking patterns, particularly during the July–August peak period.

**6. Introduce Segment-Based Pricing Strategies**

Evaluate pricing separately across hotel types and market segments while considering booking volume, distribution costs and overall profitability.

**7. Optimize Stay-Based Services**

Develop suitable extended-stay packages and tailor services according to the different stay patterns of City and Resort Hotel guests.

**8. Improve Data Quality and Monitoring**

Introduce automated data validation, investigate unusual booking records and establish regular monitoring of missing values and duplicate records.

---

## ⚠️ Project Limitations

- The analysis is based on historical booking records and does not establish causal relationships.
- Booking counts do not directly represent actual hotel occupancy.
- Room inventory and capacity information are unavailable, so occupancy rates cannot be calculated.
- ADR represents Average Daily Rate and should not be interpreted as total revenue.
- Exact duplicate removal assumes repeated identical rows represent duplicate records.
- Certain unusual observations and small customer/deposit groups require further investigation.
- Statistical significance does not necessarily imply a strong practical relationship.

---

## 🏁 Final Conclusion

The Hotel Harmony project demonstrates how exploratory data analysis can transform raw hotel booking records into meaningful business insights.

The analysis identified important relationships involving hotel type, customer category, booking lead time, deposit arrangements, market segments, pricing and seasonal booking patterns.

Statistical testing further supported the presence of a significant association between hotel type and cancellation status, while correlation analysis identified a weak positive relationship between lead time and cancellation behaviour.

The findings suggest that hotels can improve operational planning, cancellation management and pricing decisions by adopting data-driven strategies.

Overall, this project demonstrates the practical application of Python, Pandas, NumPy, Matplotlib, Seaborn, exploratory data analysis and statistical methods to investigate real-world business problems and support informed decision-making.

---

## 📁 Repository Structure

```text
├── Visualization/
│   ├── [Notebook chart screenshots]
│   └── ...
├── Hotel_Booking_EDA.ipynb
└── Hotel_Harmony_Business_Insights.docx
├── README.md
├── hotel_bookings.csv
```

## 👨‍💻 Author

**Md Ziaul Haque**

Data Analyst | Business Analyst

- **LinkedIn:** [mdziaulhaque-datascience](https://www.linkedin.com/in/mdziaulhaque-datascience/)
- **GitHub:** [md-ziaul-haque-ds](https://github.com/md-ziaul-haque-ds)

---

⭐ If you find this project useful, feel free to explore the repository and its analytical findings.
