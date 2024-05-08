# ISyE 3030 Project: Analyzing Player Performance and Team Success in the WNBA

## Introduction
The goal of this project is to analyze how draft choices impact player performance and team success in the WNBA. Specifically, the project aims to identify if the draft round and pick correlate with key performance indicators for players and consequently, the overall team success in subsequent seasons. This project was inspired by the recent WNBA draft for the 2024 season.

### Team Members
- **Sydney Bice**
- **Johanna Lumbantobing**

## Data Collection and Preprocessing
This project utilizes publicly available data sourced from two main websites: Across the Timeline and Basketball Reference. We collected four types of data:

1. **Draft Data (2019-2023):**
   - Comprehensive details of WNBA drafts from 2019 to 2023, such as draft round picks, players, and teams.
   - **Citation:** Across the Timeline. (n.d.). WNBA Drafts. Retrieved April 20, 2024, from [acrossthetimeline.com](https://www.acrossthetimeline.com/wnba/drafts.html#season=2020)

2. **Player Award Data (2020-2023):**
   - Major WNBA awards from 2020 to 2023, with entries labeled by year.
   - **Citation:** Across the Timeline. (n.d.). WNBA Awards. Retrieved April 10, 2024, from the specific URL above.

3. **Player Performance Data (2020-2023) from Basketball Reference:**
   - Detailed player statistics for WNBA seasons, with each year's data in separate sheets.
   - **Citation:** Basketball Reference. (2023). WNBA Player Totals. Retrieved April 10, 2024, from [basketball-reference.com](https://www.basketball-reference.com/wnba/years/2023_totals.html)

4. **Playoff Performance Data (2020-2023) from Basketball Reference:**
   - Detailed playoff performance stats for WNBA teams.
   - **Citation:** Basketball Reference. (2021). WNBA Playoffs. Retrieved April 10, 2024, from [basketball-reference.com](https://www.basketball-reference.com/wnba/playoffs/2021.html)

### Data Preprocessing
- **Data Merging:** Merged separate datasets into a single database using pandas DataFrames.
- **Cleaning:** Individually cleaned each DataFrame before merging them on similar data columns.
- **Playoff Participation:** Checked and recorded each player's playoff participation during their draft year.
- **Awards Data:** Matched player award data and appended it to the main dataset.
- **Finalization:** Removed duplicate entries and unnecessary columns to finalize the dataset.

## Descriptive Statistics
**Visual 1: Scatter plot of draft pick number against season points**
The scatter plot displayed a moderate negative correlation of -0.485. Players drafted earlier (lower pick numbers) generally score more points than those drafted later.

**Visual 2: Heatmap of the correlation matrix**
The heatmap revealed varying degrees of correlation between draft pick number and key performance metrics (points, total rebounds, assists).

**Visual 3: Bar graph showing average points scored by drafted players segmented by draft round**
The bar graph shows that players drafted in round 1 were more likely to score more points than players drafted in later rounds.

## Statistical Inference
- **Null Hypothesis (H0):** The average points scored by players from top college programs are equal to the average points scored by players from other college programs.
- **Alternative Hypothesis (H1):** The average points scored by players from top college programs are not equal to the average points scored by players from other college programs.

We used a t-test to compare the means of two independent samples. The p-value is 0.003284, which is less than the alpha value of 0.05. Thus, we reject the null hypothesis and conclude that there is a statistically significant difference between the mean points scored by players from top college programs and other college programs.

## Regression Analysis
We performed a linear regression analysis to model the relationship between a team's average draft pick number and the team's rank for that season.

**Regression Equation:**  
y = 8.495 - 0.098x 

- **R-squared:** 0.046  
- **Interpretation:** The 8.495 represents the y-intercept, and the -0.098 is the slope. Every increase of 1 in average draft pick number results in a 0.098 decrease in team rank.

## Conclusion
This project investigates the impact of draft choices on player performance and team success in the WNBA. Our analysis shows that players selected earlier tend to exhibit stronger performance, particularly in scoring. However, regression analysis indicates that a team’s average draft pick isn't strongly linked to its season rank, suggesting that other factors, such as team dynamics and coaching, significantly influence success. Further exploration into these contextual factors could yield more comprehensive insights into team success.

## References
1. Across the Timeline. (n.d.). [WNBA Drafts](https://www.acrossthetimeline.com/wnba/drafts.html#season=2020)
2. Across the Timeline. (n.d.). [WNBA Awards](https://www.acrossthetimeline.com/wnba/awards.html)
3. Basketball Reference. (2023). [WNBA Player Totals](https://www.basketball-reference.com/wnba/years/2023_totals.html)
4. Basketball Reference. (2021). [WNBA Playoffs](https://www.basketball-reference.com/wnba/playoffs/2021.html)

## Code Structure
- `data/`: Contains the raw data collected for the project.
- `scripts/`: Python scripts for data processing and analysis.
- `images/`: Visualizations used in the analysis and report.

## Requirements
- Python 3.8+
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Statsmodels
