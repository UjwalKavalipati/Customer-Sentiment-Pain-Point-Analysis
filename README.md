# Customer-Sentiment-Pain-Point-Analysis for id4me reviews


### Google Reviews vs Reviews.io — iD4me

## Objective
The goal of this analysis is to understand how customer sentiment and concerns differ across **public** (Google Reviews) and **solicited** (Reviews.io) feedback channels, and to identify actionable insights for improving **customer trust and retention**.

Specifically, this analysis aims to:
- Compare customer sentiment across Google and Reviews.io
- Identify recurring customer pain points from negative feedback
- Highlight practical actions iD4me can take to reduce frustration and improve trust

---

## Data Sources
- **Google Reviews** (public, unsolicited feedback)
- **Reviews.io** (post-journey, prompted feedback)

> All personally identifiable information (PII) such as names has been removed.  
> Only anonymised review IDs and review text were used.

## Data cleaning
- Duplicate and null reviews are removed

## Methodology

### Sentiment Analysis
- Used **VADER (SentimentIntensityAnalyzer)**, a rule-based NLP model designed for short, emotional text.
- Each review was assigned a **compound sentiment score** in the range `[-1, +1]`.
- Sentiment labels were applied using VADER’s recommended thresholds:
  - `≥ 0.05` → Positive
  - `≤ -0.05` → Negative
  - Otherwise → Neutral

This approach avoids over-interpreting weak or ambiguous sentiment near zero.

---

### Pain Point Identification
- Keyword-based topic detection was applied **only to negative-sentiment reviews**.
- Keywords were carefully chosen to avoid overly generic terms and reduce false positives.

Pain point categories:
- **Data Quality** (e.g. incorrect, outdated)
- **Privacy & Consent** (e.g. privacy, intrusive, shared)
- **Contact Issues** (e.g. unexpected calls or emails)
- **Updates & Timeliness** (e.g. delays, slow refresh)
- **Trust** (e.g. scam, fraud)

> Keywords identify **topics**; sentiment determines whether a topic is treated as a **pain point**.

---


## Key Findings

### Sentiment Distribution by Platform
| source     | sentiment   |   count | percent   |
|:-----------|:------------|--------:|:----------|
| Google     | Negative    |       7 | 12.3%     |
| Google     | Neutral     |       5 | 8.8%      |
| Google     | Positive    |      45 | 78.9%     |
| Reviews.io | Negative    |       8 | 5.4%      |
| Reviews.io | Neutral     |      15 | 10.2%     |
| Reviews.io | Positive    |     124 | 84.4%     |

### Sentiment Comparison
- **Google reviews show over 2× higher negative sentiment** compared to Reviews.io  
  *(12.3% vs 5.4%)*
- Reviews.io displays higher positive sentiment *(84.4% vs 78.9%)*

**Interpretation:**  
- Google reviews capture **candid, frustration-driven feedback**
- Reviews.io reflects **post-success, prompted experiences**

---

### Key Customer Concerns (Negative Reviews Only)
- **Privacy & consent concerns** are more visible on Google, indicating a perception gap rather than a compliance issue
- **Update frequency** impacts perceived data quality and lead freshness
- **Contact-related issues** exist but are lower in volume and sentiment-driven

---

## Business Implications

- Monitoring Reviews.io alone would **underestimate customer frustration**
- Google reviews can act as an **early-warning system** for trust and churn risk
- Privacy concerns appear to be driven by **surprise at first contact**, not data misuse

---

## Recommendations

- Monitor Google and Reviews.io **separately**, with different weights and purposes
- Improve first-contact transparency around data sourcing and consent
- Increase transparency around update cadence to improve data confidence

---

## Limitations
- Sample sizes are moderate; insights should be treated as **directional**
- NPS was not calculated due to the absence of consistent rating data
- Keyword-based pain detection does not capture complex language nuances




## Summary
This analysis demonstrates how different feedback channels reveal **different stages of customer emotion**.  
By combining public and solicited reviews, iD4me can better detect early trust issues, respond proactively, and reduce churn risk.

---

*This project was created as an independent analysis for learning and discussion purposes.*

