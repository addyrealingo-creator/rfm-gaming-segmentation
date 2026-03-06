**User Segmentation and Profiling Analysisfor Marketing Optimization**

**_Overview_**

  This project applies RFM-based behavioral segmentation to analyze player activity in a gaming and betting platform. The objective is to identify meaningful player segments based on betting behavior and subsequently perform profiling analysis to understand the demographic and acquisition characteristics of high-value players.
  
            Raw Player Data
                 │
                 │
          Segmentation Analysis (RFM)
                 │
          Identify High-Value Segments
                 │
                 │
          Profiling Analysis
                 │
          Understand demographics + acquisition sources
                 │
          Marketing Acquisition Insights

**_Business Understanding_**

  The insights derived from this analysis can help the marketing team:

  - Identify high-value player segments
  - Understand which acquisition channels attract valuable players
  - Determine demographic patterns among profitable players
  - Improve targeting strategies for future acquisition campaigns
  - Support reactivation strategies for previously valuable players

  Ultimately, this research provides a structured framework for linking player behavior, player value, and marketing acquisition insights within a gaming and betting environment.

**_Data Understanding_**

Columns for Segmentation Analysis (RFM)
These are the behavioral variables used to compute the RFM metrics and create player segments.

| Column                          | Purpose                              | Used For                 |
| ------------------------------- | ------------------------------------ | ------------------------ |
| **Player ID**                   | Unique player identifier             | Aggregation per player   |
| **Bet Date / Transaction Date** | Determines last activity             | Recency calculation      |
| **Bet Date (Date only)**        | Counts number of active betting days | Frequency calculation    |
| **Bet Amount (Turnover)**       | Measures betting volume              |  Monetary metric         |

Columns for Profiling Analysis
Profiling is done after segmentation.
Here you analyze the characteristics of the high-value segments.

| Column              | Purpose                                            | Used For                  |
| ------------------- | -------------------------------------------------- | ------------------------- |
| Player ID           | Unique identifier                                  | Join segmentation results |
| Game ID / Game Name | Specific game played                               | Game preference analysis  |
| Product Category    | Game classification (slots, sports, lottery, etc.) | Product behavior analysis |
| Game Type           | Fast-cycle vs slow-cycle game                      | Behavioral interpretation |
| Bet Amount          | Total wagering                                     | Spending behavior         |
| GGR                 | Revenue generated                                  | Player value measurement  |
| Age                 | Demographic analysis                               | Player profiling          |
| Gender              | Demographic analysis                               | Player behavior patterns  |
| Region              | Geographic analysis                                | Market targeting          |
| Platform Usage      | Mobile / web / app                                 | Device preference         |
| Acquisition Source  | Marketing campaign origin                          | Acquisition performance   |

  - The analysis window covers 12 months to capture complete player activity cycles and mitigate seasonal bias caused by promotional spikes. Additionally, results were interpreted alongside historically stable months to better understand baseline player behavior outside heavy promotional periods.
  - Different games have varying session speeds, betting frequency, and engagement cycles, which may influence the Recency and Frequency metrics observed in the segmentation stage.
  - Data used in this repository is anonymized and structured to demonstrate methodology without exposing proprietary information.

**_Technologies_**

  Key technologies required for this project
  - SQL (aggregation, joins, window functions, CASE statements)
  - Python (data wrangling and analysis)
  - Pandas / NumPy (data manipulation)
  - Matplotlib / Seaborn (visualization)
  - Git & GitHub 

**_Approach_**

1. Data Extraction and Preparation

Transaction-level betting data is aggregated into player-level metrics to enable behavioral analysis. Demographic attributes and acquisition source data are then merged with the transactional dataset to provide additional context for profiling. The following preprocessing steps are performed:

  - Aggregate transaction-level betting data into player-level metrics
  - Merge demographic information and acquisition source data
  - Filter records within a defined analysis window to ensure behavioral relevance
  - Perform data validation to remove duplicates and inconsistencies

This process results in a structured dataset containing both behavioral and contextual attributes for each player.

2. RFM Metric Calculation

  - Recency (R)
Measures the number of days since a player's most recent betting activity. Players with more recent activity indicate higher engagement.
  - Frequency (F)
Represents the number of distinct active betting days during the analysis period. Higher frequency indicates stronger engagement and habitual platform usage.
  - Monetary (M)
Measures the total revenue generated by a player, typically represented by their .


3. RFM Scoring and Segmentation

To standardize the behavioral metrics across the player population, quintile-based scoring is applied to each RFM dimension.
Players are ranked and assigned scores from 1 to 5, where:

  - Recency: more recent activity receives a higher score
  - Frequency: more active betting days receive a higher score
  - Monetary: higher GGR contribution receives a higher score

Each player receives a composite RFM score, represented as a three-digit code (e.g., 555 indicates the highest engagement and value across all dimensions).
Based on the resulting RFM scores, players are categorized into five key behavioral segments:

| Segment               | RFM Profile                          | Behavior / Description                                            | Marketing Focus                                          |
| --------------------- | ------------------------------------ | ----------------------------------------------------------------- | -------------------------------------------------------- |
| Champions / Top Value | R ≥ 4, F ≥ 4, M ≥ 4                  | Most active players with the highest spending and recent activity | VIP retention, exclusive rewards, lookalike acquisition  |
| Loyal Players         | R ≥ 3, F ≥ 4, M ≥ 3                  | Consistent players with stable betting behavior                   | Upsell, engagement programs, cross-sell offers           |
| Potential Loyalists   | R ≥ 4, F 2–3, M 2–3                  | Recently active players showing potential for growth              | Incentivize engagement, first-time high-value promotions |
| At-Risk Players       | R ≤ 2, F ≥ 3, M ≥ 3                  | Previously valuable players who have become inactive              | Reactivation campaigns, win-back incentives              |
| Dormant / Lapsed      | R ≤ 2, F ≤ 2                         | Players with minimal or inactive engagement                       | Low-cost win-back or generic re-engagement campaigns     |


This segmentation framework helps identify top-performing players, players with growth potential, and players at risk of churn.

4. Player Profiling for Acquisition Insights

After identifying behavioral segments, profiling analysis is conducted to understand the characteristics of players within each segment, particularly high-value segments.

Key profiling dimensions include:
  - Demographics: age, gender, and geographic region
  - Acquisition source: marketing channels or campaigns that generated the player
  - Platform usage: device type or access platform
  - Game preference: types of games played (e.g., fast-cycle vs slow-cycle games)

5. Marketing Targeting Insights

By examining the profiles of high-value segments, the study identifies common patterns that can guide future acquisition and re-acquisition efforts.
  - Identification of demographic traits associated with high-value players
  - Analysis of acquisition channels that generate the most valuable players
  - Identification of player behaviors and product preferences linked to higher engagement
  - Development of target player profiles that can support lookalike acquisition campaigns

These insights enable marketing teams to design more targeted acquisition strategies, improve campaign efficiency, and optimize marketing budget allocation.

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
