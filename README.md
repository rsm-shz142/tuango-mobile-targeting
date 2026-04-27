# Tuango: Targeting Mobile App Messages

RFM-based logistic regression targeting model for Tuango's karaoke deal
campaign — selective targeting delivered 8× more profit than mass messaging.

## Background

Tuango, a Chinese deal-of-the-day platform, ran a karaoke deal campaign
via mobile app push messages. Each message carries a hidden cost of 9 RMB
— customers who receive too many irrelevant offers may block future messages
permanently. After a 20,908-customer test, 397,252 customers remained for
rollout. The question: target everyone, or only likely buyers?

## Methodology

- Built a logistic regression model predicting purchase probability using
  RFM variables (Recency, Frequency, Monetary), Age, Gender, and Music
  purchase history
- Built a linear regression on buyers only to predict order size
- Derived a breakeven response rate: Cost per message / Margin per response
- Targeted only customers with predicted purchase probability above breakeven
- Validated results on actual post-rollout data (all 397,252 customers contacted)

## Key Results

| Strategy | Profit (RMB) | ROME |
|---|---|---|
| Target all customers | 111,713 | 3.1% |
| Target by logit model | 887,423 | 56.6% |

Logit-based targeting delivered 8× more profit and 18× better ROME.
Results confirmed on actual rollout data — no overfitting observed.

## Key Finding

Music purchase history and gender were the strongest predictors of deal
response. Order size was difficult to predict (low R-squared), but this
is expected — the key lever is correctly identifying who buys, not how much.

## Files

- `tuango.ipynb`: Full analysis notebook (test sample + rollout evaluation)
- `data/`: Deal campaign datasets (pre and post rollout)

## Tools

Python · Polars · pyrsm · plotnine · Logistic Regression ·
Linear Regression · RFM Analysis · Permutation Importance ·
Partial Dependence Plots · ROME
