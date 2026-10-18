# Football Scouting Analytics & AI

## Project Overview

This project explores how data analytics can support recruitment decisions for a hypothetical medium-sized football club operating with a limited budget.

The objective is to identify promising young players who offer a balance of current ability, future potential, tactical suitability, and estimated financial cost.

The project includes a Jupyter Notebook for data analysis and an interactive HTML dashboard for exploring recruitment scenarios.

## Business Problem

A football club needs to identify affordable young talent without relying solely on player reputation or overall ratings.

The analysis addresses three key questions:

1. How do market value, player quality, and potential relate to each other?
2. Which young players meet the club's assumed recruitment and financial requirements?
3. Which shortlisted strikers offer attractive scouting performance relative to estimated recruitment cost?

## Dataset

The project uses a historical FIFA video game player dataset.

- Total players: 17,954
- Total columns: 51
- Missing market values: 255
- Players with recorded market values and wages: 17,699

**Important:** FIFA ratings, valuations, and wages are game-based estimates, not verified real-world scouting or transfer data.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- HTML interactive dashboard

## Analysis Workflow

### 1. Data Exploration and Cleaning

- Examined dataset structure and descriptive statistics.
- Checked duplicate records and missing values.
- Investigated missing market values across age groups.
- Preserved players with missing financial information for analyses where those fields were not required.

### 2. Exploratory Data Analysis

- Segmented players by market value.
- Compared current ability and potential across market-value groups.
- Examined patterns among players aged 23 or younger.

### 3. Recruitment Shortlist

Applied hypothetical recruitment requirements:

| Criterion | Requirement |
|---|---|
| Age | 23 or younger |
| Potential | At least 80 |
| Market value | Up to €3 million |
| Weekly wage | Up to €10,000 |
| Overall rating | At least 68 |

These criteria produced a shortlist of 109 players, including 13 strikers.

### 4. Striker Scouting Model

Developed a weighted scoring model for a hypothetical counter-attacking playing style.

**Original model:**

- Sprint speed: 45%
- Finishing: 35%
- Positioning: 20%

A sensitivity analysis also tested an alternative model with weights of 30%, 40%, and 30%, respectively.

### 5. Estimated Three-Year Cost

Estimated financial commitment using:

**Estimated cost = FIFA market value + (weekly wage × 52 × 3)**

This is a simplified financial proxy, not a prediction of actual transfer expenditure.

## Key Findings

- Higher market-value groups generally showed higher average overall ratings and potential among young players.
- D. Oberlin achieved the highest score in the original striker model, with 79.25 points.
- J. Ardaiz achieved 77.05 points, with an estimated three-year cost of €2.312 million, compared with €3.460 million for Oberlin.
- Changing the scoring weights moved Ardaiz from fourth to second place, demonstrating how tactical priorities affect player rankings.

## Recruitment Recommendation

J. Ardaiz was identified as a promising candidate for further scouting evaluation based on his balance of tactical score and estimated cost.

This is not a definitive signing recommendation. Additional scouting, real-world performance analysis, and financial verification would be necessary.

## Interactive Dashboard

The project includes an interactive dashboard with three sections:

- **General Analysis:** Dataset overview, player segments, and data quality.
- **Striker Selection:** Interactive scouting weights, estimated cost limits, rankings, and recruitment recommendations.
- **Player Finder:** Search and filter players by age, position, ability, potential, market value, wages, and other available attributes.

The dashboard uses an embedded snapshot of the dataset and does not automatically refresh from the CSV file.

## Project Structure

```text
fifa_analysis/
├── Football_Scouting_Analysis.ipynb
├── Scouting_dashboard.html
├── fifa_players.csv
├── requirements.txt
└── README.md
```

## How to Run

1. Download or clone the repository.
2. Install the required Python libraries:

```bash
pip install -r requirements.txt
```

3. Open the Jupyter Notebook:

```text
Football_Scouting_Analysis.ipynb
```

4. Run the notebook cells in order. The dataset must remain in the same folder as the notebook.
5. Open the HTML dashboard in a web browser:

```text
Scouting_dashboard.html
```

## Limitations

- The dataset contains historical FIFA game estimates rather than current real-world football data.
- Scouting weights are subjective assumptions and have not been validated against match performance.
- Estimated costs exclude additional transfer-related expenses.
- Injuries, contract conditions, player availability, and actual match statistics are not included.
- Recruitment recommendations are preliminary and require professional verification.

## Conclusion

The project demonstrates how Python-based data analysis, financial constraints, scoring models, and interactive visualizations can support structured football recruitment decisions.

Its primary value is demonstrating an end-to-end analytical workflow, from data quality assessment and exploratory analysis to business insights and decision support.