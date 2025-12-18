# Will the Customer Accept the Coupon?

## Project Overview

This project analyzes data from the UCI Machine Learning Repository to understand what factors influence whether a driver accepts a coupon delivered to their cell phone while driving. The data was collected via a survey on Amazon Mechanical Turk, describing various driving scenarios and asking participants if they would accept different types of coupons.

**Key Question:** What distinguishes drivers who accept coupons from those who don't?

---

## Dataset

- **Source:** UCI Machine Learning Repository (Amazon Mechanical Turk survey)
- **Size:** 12,684 observations, 26 features
- **Target Variable:** `Y` (1 = accepted, 0 = rejected)
- **Coupon Types:** Coffee House, Restaurant(<$20), Carry out & Take away, Bar, Restaurant($20-$50)

---

## Key Findings

### Overall Acceptance Rate
- **56.8%** of all coupons were accepted
- Acceptance varies significantly by coupon type

### Acceptance Rate by Coupon Type

| Coupon Type | Acceptance Rate |
|-------------|-----------------|
| Carry out & Take away | 73.5% |
| Restaurant(<$20) | 70.7% |
| Coffee House | 49.9% |
| Restaurant($20-$50) | 44.1% |
| Bar | 41.0% |

---

## Bar Coupon Analysis

Bar coupons had the **lowest acceptance rate (41%)** of all coupon types. Key factors influencing acceptance:

### Visit Frequency is the Strongest Predictor
- Drivers visiting bars **>3 times/month**: **77%** acceptance
- Drivers visiting bars **≤3 times/month**: **37%** acceptance

### Age + Frequency Matters
- Drivers **>25 years old** who visit bars **>1x/month**: **69%** acceptance
- All others: **33%** acceptance

### Passengers Make a Difference
- With **Friends**: **56%** acceptance
- **Alone**: **41%** acceptance
- With **Kids**: **21%** acceptance (lowest!)

### Hypothesis
Bar coupon acceptance is driven by **lifestyle fit**. Drivers who already incorporate bar visits into their social routine are 2-3x more likely to accept. The coupon reinforces existing behavior rather than creating new behavior.

---

## Coffee House Coupon Analysis (Independent Investigation)

Coffee House coupons had a **50% acceptance rate**, slightly below average. Key findings:

### Visit Frequency Dominates (Again!)
- **>8 visits/month**: **66%** acceptance
- **Never visit**: **34%** acceptance

### Time of Day Matters
- **10AM** (morning rush): **58%** acceptance ☕
- **10PM** (late night): **43%** acceptance

### Age Trends Younger
- **Ages 21-26**: **54-56%** acceptance
- **Ages 50+**: **46%** acceptance

### Social Context
- With **Friends**: **60%** acceptance (highest!)
- With **Kids**: **43%** acceptance (lowest)

### Hypothesis
Coffee House coupon acceptance is driven by **lifestyle alignment**. Young drivers who already frequent coffee shops and are in social situations (with friends) during mid-morning hours are most receptive.

---

## Actionable Recommendations

### For Bar Coupons 🍺
**Target:**
- Drivers with history of bar visits (>1x/month)
- Ages 21-35
- Traveling with friends or partner
- Evening/social hours

**Avoid:**
- Drivers with children as passengers
- Those who rarely/never visit bars

### For Coffee House Coupons ☕
**Target:**
- Existing coffee house visitors (>1x/month)
- Ages 21-30
- Traveling with friends
- Mid-morning hours (10AM optimal)

**Avoid:**
- Late night drivers (10PM)
- Drivers with kids
- Non-coffee drinkers

---

## Technical Details

### Tools Used
- **Python 3.x**
- **pandas** - data manipulation
- **NumPy** - numerical operations
- **Matplotlib & Seaborn** - visualizations

### Files
```
├── README.md                 # This file
├── data/
│   └── coupons.csv          # Raw dataset
└── coupon_analysis.ipynb    # Jupyter notebook with full analysis
```

---

## Next Steps

1. **Build a predictive model** - Use logistic regression or decision trees to predict coupon acceptance
2. **Feature engineering** - Create interaction features (e.g., age × visit frequency)
3. **A/B testing recommendations** - Test targeted coupon delivery based on findings
4. **Analyze other coupon types** - Deep dive into Restaurant($20-$50) low acceptance

---

## Author

Shawn - UC Berkeley ML/AI Professional Certificate Program

## Acknowledgments

- UCI Machine Learning Repository for the dataset
- Amazon Mechanical Turk survey participants
