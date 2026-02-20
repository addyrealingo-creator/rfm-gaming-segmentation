# rfm-gaming-segmentation
This project showcases an RFM-based customer segmentation framework commonly used in gaming and digital platforms to support retention and targeted marketing strategies.

**RFM-Based Player Segmentation for Marketing Optimization**

_Overview_

This project implements an RFM (Recency, Frequency, Monetary) analysis framework to segment players based on behavioral and transactional data.
The objective is to support marketing strategy by identifying high-value, loyal, at-risk, and dormant player segments for targeted campaign optimization and retention initiatives.
This repository demonstrates end-to-end analytical workflow including data extraction, transformation, segmentation logic, and business interpretation.

_Business Understanding_

Marketing teams require structured customer segmentation to:
- Improve campaign targeting precision
- Increase player retention
- Optimize channel budget allocation
- Identify high-value and at-risk players
- Support revenue growth strategies
This project applies RFM modeling to transform raw transactional data into actionable player segments that can guide CRM, reactivation campaigns, VIP prioritization, and lifecycle marketing initiatives.

_Data Understanding_

The dataset includes aggregated player-level transactional and activity data such as:
| Column                          | Purpose                               | Used For       |
| ------------------------------- | ------------------------------------- | -------------- |
| **Player ID**                   | Unique player identifier              | Aggregation    |
| **Bet Date / Transaction Date** | To compute last bet date              | Recency        |
| **Bet Date (Date only)**        | To count distinct active betting days | Frequency      |
| **Bet Amount (Turnover)**       | Optional but useful                   | GGR validation |
| **Payout Amount**               | Needed to compute GGR                 | Monetary       |
| **GGR** (if already computed)   | Direct monetary metric                | Monetary       |

The analysis focuses on a defined time window to ensure relevance and consistency in behavioral scoring.
Dataused in this repository is anonymized and structured to demonstrate methodology without exposing proprietary information.

_Technologies_

This project demonstrates proficiency in:
- SQL (aggregation, joins, window functions, CASE statements)
- Python
- Pandas
- NumPy
- Matplotlib / Seaborn (for visualization)
- Protos 
- Git & GitHub

_Approach_

1. Data Extraction
- Aggregated transaction-level data into player-level metrics
- Filtered records within defined analysis window (2nd half of 2025)
- Validated data quality and removed inconsistencies

3. RFM Metric Calculation
- Recency (R): Days since last bet
- Frequency (F): Active Days of Betting
- Monetary (M): GGR per player

4. Scoring Methodology
- Applied quintile-based scoring (1–5 scale) on population
- Assigned composite RFM scores (e.g., 555 = highest value segment)
  - Recency: latest transaaction = high value
  - Frequency: more active days = high score
  - Monetary: high ggr = high score
- Standardized scoring logic for reproducibility

5. Segmentation Framework
Players were categorized into actionable marketing segments such as:
- Champions
- Loyal Players
- Potential Loyalists
- At Risk
- Dormant

5. Business Interpretation
Each segment supports specific marketing strategies:
- **Champions**: VIP retention and exclusive rewards
- **Loyal Players**: Upsell and engagement programs
- **At Risk**: Targeted reactivation campaigns
- **Dormant**: Win-back initiatives

_Strategic Value_

This segmentation framework enables:
- Data-driven campaign targeting
- Efficient marketing budget allocation
- Improved player lifecycle management
- Enhanced retention and revenue optimization
RFM modeling serves as a foundational analytics layer that can later integrate with predictive models such as churn prediction or customer lifetime value (CLV) estimation.

_Credits_

Mentorship and guidance provided by the Enterprise Analytics team, especially Teammate Christopher Martinez, and Sir Robinbin, our Head
RFM methodology inspired by widely adopted CRM and marketing analytics frameworks.

_Future Enhancements_

- Integration with predictive churn modeling
- Automated dashboard reporting
- Campaign performance A/B testing per segment
- CLV-based segmentation overlay
