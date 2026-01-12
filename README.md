# Regork Grocery Analysis (Complete Journey Retail Data)

This project analyzes the **Complete Journey** grocery shopping dataset (via the **`completejourney`** R package) to uncover **revenue growth opportunities** for a fictional national grocery chain, **Regork**.

It is designed to be **recruiter-friendly**: you’ll see the business problem, the dataset context, the analytics approach, and exactly how to reproduce the results locally.

**Final report (RPubs):** https://rpubs.com/SukanyaChatterjee/1383843  
**Dataset documentation:** https://bradleyboehmke.github.io/completejourney/index.html

---

## Problem statement (Regork’s goal)
Regork operates in a low-margin retail environment where small improvements in **pricing, promotions, and retention** can create meaningful business impact.

This project answers:
- What are Regork’s core performance signals (AOV, basket size, purchase frequency)?
- Which customer behaviors drive revenue (repeat vs occasional shoppers)?
- How do sales patterns change over time (weekly/seasonality)?
- Where can promo/pricing actions improve performance?

---

## Dataset overview (Complete Journey / 84.51°)
The Complete Journey dataset includes **one year of transactions** for **2,469 households**, along with product metadata and optional marketing/demographic information.

Typical tables available through the package:
- `transactions` / `transactions_sample` — household purchases (line items in baskets)
- `products` — product metadata (descriptions/attributes)
- `promotions` / `promotions_sample` — promotion/placement signals
- `demographics` — household demographics (if used)
- `campaigns`, `campaign_descriptions` — campaign history (if used)
- `coupons`, `coupon_redemptions` — coupon usage (if used)

> If your repo does not include raw data files, this README uses `completejourney` to load data directly in R.

---

## What I did (end-to-end workflow)
### 1) Data preparation
- Loaded data from `completejourney`
- Cleaned and standardized keys (households, products, baskets, time variables)
- Joined transactions with product metadata for product/category-level insights

### 2) KPI building (retail fundamentals)
Built KPIs used throughout the analysis:
- **AOV (Average Order Value)** = total sales / number of baskets
- **Basket Size** = quantity or unique items per basket (depending on the approach)
- **Purchase Frequency** = baskets per household (or trips per time period)

### 3) Customer + seasonality analysis
- Compared customer cohorts based on shopping behavior
- Identified weekly/seasonal demand patterns
- Highlighted periods/segments where targeted actions can drive lift

### 4) Business recommendations
- Promo strategy recommendations (where promos help vs where they likely don’t)
- Pricing opportunities based on observed purchase patterns
- Customer-focused recommendations (retention and repeat purchase drivers)

---

## Tech stack
- **R / RStudio**
- **tidyverse** (dplyr, ggplot2, etc.)
- **completejourney** (dataset access)
- **R Markdown** (reproducible final report)

---

## How to run (reproduce the project locally)

## Prerequisites

-R (4.x recommended)

-RStudio (recommended)

## Step 1- Install packages

-Open R/RStudio and run:

-install.packages("completejourney")
-install.packages("tidyverse")

## Step 2- Load libraries

-library(completejourney)
-library(tidyverse)

## Step 3- Load the dataset

You can run using sample tables (fast) or full tables (recommended).

## Option A: Sample tables (fastest)
data("transactions_sample")
data("products")
data("promotions_sample")

transactions <- transactions_sample
promotions   <- promotions_sample

## Option B: Full tables (recommended)
transactions <- get_transactions()
promotions   <- get_promotions()

data("products")

# Optional 

data("demographics")
data("coupons")
data("coupon_redemptions")
data("campaigns")
data("campaign_descriptions")

## Step 4- Run the analysis


Open Regork_Final_Project.Rmd in RStudio

Click Knit (HTML is typical)

Or run via console:

rmarkdown::render("Regork_Final_Project.Rmd")

├─ outputs/                              
└─ README.md

## Results 

The final report includes:

KPI summary for Regork (AOV, basket behavior, purchase frequency)

<img width="1141" height="479" alt="image" src="https://github.com/user-attachments/assets/a64284c6-0d08-4695-8523-6d3a5d4ffb5d" />


Customer behavior patterns (repeat vs occasional signals)

<img width="1174" height="528" alt="image" src="https://github.com/user-attachments/assets/31bc4401-d81c-462e-a213-3c7dc5bfd9f1" />


Seasonality / weekly patterns (timing-based insights)

<img width="1230" height="560" alt="image" src="https://github.com/user-attachments/assets/de520f9e-7922-4f76-8c49-c7789f731a8b" />


-Actionable recommendations tied to findings

<img width="1201" height="563" alt="image" src="https://github.com/user-attachments/assets/63ffd898-6e9f-41e0-bf1b-53bfc3911ee4" />


📌 Read the final report here: https://rpubs.com/SukanyaChatterjee/1383843
