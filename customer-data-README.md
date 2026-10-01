# Home-goods customer panel

This teaching case follows 10,000 customers of a fictional online home-goods
retailer. A household survey is linked to shopping, browsing, and email records.
Each panel member has a full 12-month customer history and at least one earlier
website visit. All dollar values are US dollars.

The retailer randomly assigns 5,000 customers to receive a promotional email and
5,000 to a control group that receives no campaign email. It records whether each
customer buys anything, and their total spending, during the following 30 days.
Earlier purchases, browsing, and email engagement precede assignment.

Use `home_goods_customers.csv` with the accompanying `data_dictionary.md`.
One row represents one customer. Empty cells indicate missing survey responses;
zeros are observed values. The file is UTF-8 CSV, approximately 0.8 MB.

```r
customers <- read.csv("home_goods_customers.csv", na.strings = "")
customers$Region <- factor(customers$Region)
customers$Education <- factor(customers$Education)
```

These are **semi-synthetic teaching data**. Customer characteristics have
fictional meanings and distributions. Spending, treatment, and campaign outcomes
are simulated. They describe neither actual Criteo customers nor real retailer
performance. The new experimental assignment is independent of customer history.

## Attribution and reuse

Adapted from Criteo AI Lab's [Criteo Uplift Prediction Dataset, v2.1](https://ailab.criteo.com/criteo-uplift-prediction-dataset/).
See Diemert, Betlei, Renaudin, and Amini (2018), *A Large Scale Benchmark for
Uplift Modeling*, AdKDD and TargetAd Workshop; [expanded description](https://arxiv.org/abs/2111.10106).

Changes include stratified subsampling, fictional feature transformations,
simulated historical spending, a new randomized experiment, simulated campaign
outcomes, and introduced missing survey values. Original anonymized feature
meanings have not been recovered. Source data and this adapted dataset are
provided under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
Keep this attribution and modification notice with redistributed data.
