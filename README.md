[README.md](https://github.com/user-attachments/files/32188780/README.md)
# Detecting Unusual Activity on Wykop.pl

A data-analysis project that explores potentially unusual, automated or coordinated user activity on **Wykop.pl**, with a focus on voting behaviour for posts tagged `#polska` in Q1 2026.

## Objective

Build a reusable pipeline that collects public Wykop API data, prepares it for analysis and identifies accounts with anomalous behavioural patterns. The project is exploratory: it flags candidates for further review; it does not prove that an account is a bot.

## Data

The analysis uses public data from the Wykop API, including:

- Post metadata: ID, author, publication time and tags
- Upvotes and downvotes, including voter, vote time and downvote reason
- Public user-profile activity data

The final joined dataset contains **1,088 posts**, **14 columns** and **33,606 unique users**.

## Approach

1. Retrieve posts and vote metadata through the Wykop API
2. Clean, transform and join data in pandas
3. Create user-level features covering voting volume, vote direction, activity time, voting reasons and topic patterns
4. Explore outliers using Python and Orange Data Mining

Examples of signals investigated include a very high activity volume, an extreme imbalance between positive and negative votes, high night-time voting share, and exclusively positive or negative voting patterns.

## Tech stack

- Python
- Jupyter Notebook
- pandas
- NumPy
- Wykop API / `wykop_sdk_reloaded`
- Orange Data Mining
- CSV

## Results

The project produced a repeatable workflow for analysing Wykop activity across other tags or time periods. Exploratory analysis identified a small group of accounts that differed strongly from typical users in the scale, timing or direction of their voting activity.

## Running the project

1. Clone this repository
2. Install the required Python packages
3. Add your Wykop API credentials locally — **never commit API keys or secrets**
4. Open and run the Jupyter notebook

```bash
pip install pandas numpy wykop-sdk-reloaded jupyter
jupyter notebook
```

## Notes

- Data comes from public API endpoints and may change as the platform or API changes.
- Any account-level findings should be interpreted carefully and validated with additional evidence.
- This repository is intended for educational and portfolio purposes.

## Author

**Michał Pędzimaż**  
Data Science postgraduate project, AGH University of Krakow (2026)
