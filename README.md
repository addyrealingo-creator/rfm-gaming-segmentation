# rfm-gaming-segmentation
This project showcases an RFM-based customer segmentation framework commonly used in gaming and digital platforms to support retention and targeted marketing strategies.

**RFM-Based Player Segmentation for Marketing Optimization**

_📌 Overview_

This project implements an RFM (Recency, Frequency, Monetary) analysis framework to segment players based on behavioral and transactional data.
The objective is to support marketing strategy by identifying high-value, loyal, at-risk, and dormant player segments for targeted campaign optimization and retention initiatives.
This repository demonstrates end-to-end analytical workflow including data extraction, transformation, segmentation logic, and business interpretation.

_🧠 Business Understanding_

Marketing teams require structured customer segmentation to:
- Improve campaign targeting precision
- Increase player retention
- Optimize marketing budget allocation
- Identify high-value and at-risk players
- Support revenue growth strategies
This project applies RFM modeling to transform raw transactional data into actionable player segments that can guide CRM, reactivation campaigns, VIP prioritization, and lifecycle marketing initiatives.

_📊 Data Understanding_

The dataset includes aggregated player-level transactional and activity data such as:
- Player ID
- Registration date
- Transaction dates
- Deposit amounts
- Betting activity
-  frequency
The analysis focuses on a defined time window to ensure relevance and consistency in behavioral scoring.
Dataused in this repository is anonymized and structured to demonstrate methodology without exposing proprietary information.

_⚙️ Technologies_

This project demonstrates proficiency in:
- SQL (aggregation, joins, window functions, CASE statements)
- Python
- Pandas
- NumPy
- Matplotlib / Seaborn (for visualization)
- Jupyter Notebook
- Power BI / Tableau (optional visualization layer)
- Git & GitHub

_🛠 Setup_

To replicate this project locally:
Clone this repository:
git clone https://github.com/addyrealingo-creator/rfm-gaming-segmentation.git

_Install required dependencies:
pip install pandas numpy matplotlib seaborn
Open the notebook:
jupyter notebook rfm_analysis.ipynb
Update database connection string (not included for security and compliance reasons).
Note: Database credentials and proprietary datasets are excluded._

_🔍 Approach_

1. Data Extraction
Aggregated transaction-level data into player-level metrics
Filtered records within defined analysis window
Validated data quality and removed inconsistencies

2. RFM Metric Calculation
Recency (R): Days since last transaction
Frequency (F): Total number of transactions
Monetary (M): Total revenue contribution or deposit value

3. Scoring Methodology
Applied quintile-based scoring (1–5 scale)
Assigned composite RFM scores (e.g., 555 = highest value segment)
Standardized scoring logic for reproducibility

4. Segmentation Framework
Players were categorized into actionable marketing segments such as:
- Champions
- Loyal Players
- Potential Loyalists
- At Risk
- Dormant

5. Business Interpretation
Each segment supports specific marketing strategies:
Champions: VIP retention and exclusive rewards
Loyal Players: Upsell and engagement programs
At Risk: Targeted reactivation campaigns
Dormant: Win-back initiatives

_📈 Strategic Value_

This segmentation framework enables:
- Data-driven campaign targeting
- Efficient marketing budget allocation
- Improved player lifecycle management
- Enhanced retention and revenue optimization
RFM modeling serves as a foundational analytics layer that can later integrate with predictive models such as churn prediction or customer lifetime value (CLV) estimation.

_📚 Credits_

Mentorship and guidance provided by the Enterprise Analytics team, especially Sir Christopher Martinez, and Sir Robinbin
RFM methodology inspired by widely adopted CRM and marketing analytics frameworks.

_🚀 Future Enhancements_

- Integration with predictive churn modeling
- Automated dashboard reporting
- Campaign performance A/B testing per segment
- CLV-based segmentation overlay
