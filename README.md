**RFM-Based Player Segmentation for Marketing Optimization**

**_Overview_**

  This project leverages an RFM (Recency, Frequency, Monetary) analysis framework to profile high-value players and support data-driven marketing acquisition strategies. By understanding who the top-performing players are and their behavioral patterns, the Marketing team can design targeted campaigns to attract similar high-value players and re-engage lapsed users effectively.

**_Business Understanding_**

Marketing acquisition teams require actionable insights to:
  - Identify the characteristics of high-value players
  - Determine demographic, behavioral, and transactional profiles
  - Optimize acquisition and re-acquisition campaigns
  - Increase return on marketing investment (ROI) by targeting players most likely to convert or return
  - Inform creative and channel strategy for new user acquisition
RFM modeling provides a structured approach to segmenting players based on engagement and monetary behavior, which becomes a foundation for targeted acquisition efforts.

**_Data Understanding_**

The dataset includes aggregated player-level transactional and activity data such as:
| Column                          | Purpose                               | Used For           |
| ------------------------------- | ------------------------------------- | ------------------ |
| **Player ID**                   | Unique player identifier              | Aggregation        |
| **Bet Date / Transaction Date** | To compute last activity              | Recency            |
| **Bet Date (Date only)**        | To count distinct active betting days | Frequency          |
| **Bet Amount (Turnover)**       | Optional but useful                   | Monetary           |
| **Payout Amount**               | Needed to compute GGR                 | Monetary           |
| **GGR** (if already computed)   | Direct monetary metric                | Monetary           |
| **Demographics**                | Age, gender, region, platform usage   | Profiling          |
| **Acquisition Source**          | Channel or campaign of origin         | Campaign Targeting |
The analysis focuses on a defined time window to ensure relevance and consistency in behavioral scoring.
Dataused in this repository is anonymized and structured to demonstrate methodology without exposing proprietary information.

**_Technologies_**

Key technologies required for this project
  - SQL (aggregation, joins, window functions, CASE statements)
  - Python (data wrangling and analysis)
  - Pandas / NumPy (data manipulation)
  - Matplotlib / Seaborn (visualization)
  - Git & GitHub 

**_Approach_**

1. Data Extraction
- Aggregated transaction-level data into player-level metrics
- Merge demographic and acquisition source data
- Filter records within a defined analysis window
2. RFM Metric Calculation
- Recency (R): Days since last bet
- Frequency (F): Active days of betting
- Monetary (M): GGR per player
3. Scoring Methodology
- Applied quintile-based scoring (1–5 scale) on population
- Assigned composite RFM scores (e.g., 555 = highest value segment)
  - Recency: latest transaaction = high value
  - Frequency: more active days = high score
  - Monetary: high ggr = high score
- Identify top-performing, high-potential, and lapsed players
4. Player Profiling for Acquisition
  - Combine RFM segments with demographics and acquisition source
  - Analyze gender, age, region, and channel patterns for high-value players
  - Identify traits of players most likely to convert or return
5. Marketing Targeting Insights
  - Create profiles of high-value players to guide campaign targeting
  - Recommend channels, creative types, and audience segments for re-acquisition
  - Enable lookalike modeling for new user acquisition

**_Strategic Value_**

  - Supports targeted marketing campaigns by identifying high-value player profiles
  - Optimizes acquisition spend by focusing on high-potential audiences
  - Improves conversion and re-engagement by using behavioral insights
  - Bridges transactional data with demographic and channel intelligence

**_Credits_**

Mentorship and guidance provided by the Enterprise Analytics team, especially Teammate Christopher Martinez, and Sir Robinbin, our Head. RFM methodology inspired by widely adopted CRM and marketing analytics frameworks.

**_Future Enhancements_**

- Integration with predictive churn modeling
- Automated dashboard reporting
- Campaign performance A/B testing per segment
- CLV-based segmentation overlay
