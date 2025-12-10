# Employee Sentiment Analysis – Final LLM Assessment

## 1. Project Overview

This project analyzes internal email text to understand employee sentiment over time.
Using the provided `test(in).csv` dataset (unlabeled emails), we:

- Clean and combine `Subject` + `body` into a single text field
- Perform sentiment analysis (Positive / Neutral / Negative) using TextBlob
- Compute monthly sentiment scores
- Rank employees/senders based on average sentiment
- Identify potential flight-risk employees (consistently negative senders)
- Build a linear regression model (with scikit-learn) to model sentiment trends over time

## 2. Tech Stack

- Python
- pandas, numpy
- matplotlib, seaborn
- TextBlob (for sentiment scoring)
- scikit-learn (for linear regression and evaluation)
- Jupyter Notebook

## 3. Folder & File Structure

Employee-sentiment-project/
├─ sentiment_analysis.ipynb      # main notebook with all analysis and visuals
├─ test(in).csv                  # raw email dataset
├─ README.md                     # this file
├─ .env.example                  # placeholder for environment variables (if needed)
└─ requirements.txt              # required Python packages


# 5. Methodology

# Data Cleaning
- Combined Subject and body into one text column
- Removed missing text and invalid dates
- Converted dates to datetime
- Added text length column for EDA

# Sentiment Analysis
- Used TextBlob polarity scoring

Rules:
- polarity > 0.1 → Positive
- polarity < -0.1 → Negative
- otherwise → Neutral

# Monthly Sentiment Score
- Extracted year_month from date

Mapped scores:
- Positive = 1
- Neutral = 0
- Negative = -1
- Averaged by month

 # Employee Ranking
- Grouped by sender (from)
- Calculated average sentiment score
- Identified top positive & top negative senders

# Flight-Risk Identification
- An employee is flagged as flight risk if:
- average sentiment score < 0
- more than 50% of emails are negative
- minimum email count threshold is met

# Linear Regression (scikit-learn)
- Converted date → number of days since first email
- Built regression model to analyze sentiment trend over time
- Slope interpretation:
      - Positive → sentiment improving
      - Negative → sentiment declining

 # 6. How to Use This Project

1. Open the notebook
2. Run all cells top to bottom
3. View:
     - EDA plots
     - Sentiment labels
     - Monthly score trend
     - Employee ranking
     - Flight risk list
     - Linear regression sentiment trend

# 7. Results Summary
- Sentiment distribution (Positive / Neutral / Negative)
- Monthly trend showing whether overall mood is improving or declining
- Ranked list of top positive and most negative employees
- List of potential flight risk individuals
- Trend line from regression revealing long-term sentiment direction

# 8. Author

Name: Spoorti Biradar
Email: bspoorthi804@gmail.com