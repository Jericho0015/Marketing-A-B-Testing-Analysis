# Marketing A/B Testing Analysis

This project analyzes the effectiveness of a marketing advertisement campaign using **A/B testing**. Users were split into two groups those who saw **ads** (`ad`) and those who saw a **public service announcement** (`psa`).  
The objective is to determine whether the advertisements increased conversions and how impactful the campaign was.

---
## Campaign Analysis

Marketing companies want to run successful campaigns, but the market is complex and several options can work. So normally they tun A/B tests, that is a randomized experimentation process wherein two or more versions of a variable (web page, page element, banner, etc.) are shown to different segments of people at the same time to determine which version leaves the maximum impact and drive business metrics.

The companies are interested in answering two questions:

- Would the campaign be successful?
- If the campaign was successful, how much of that success could be attributed to the ads?

---

## Project Objectives

- Determine if the marketing campaign was successful.
- Compare conversion rates between the advertisement group and the control group.
- Quantify how much of the success can be attributed to the ads.
- Validate results using statistical significance testing.

---

## Dataset Description

| Column Name       | Description |
|-------------------|-------------|
| **user_id**       | Unique identifier for each user |
| **test group**    | Shows whether the user saw an ad (`ad`) or a public service announcement (`psa`) |
| **converted**     | Whether the user purchased the product (`True` / `False`) |
| **total ads**     | Number of ads shown to the user |
| **most ads day**  | Day when the user saw the highest number of ads |
| **most ads hour** | Hour when the user saw the highest number of ads |

---

## Tools & Technologies

| Purpose | Library |
|--------|--------|
| Data Manipulation | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn` |
| Statistical Testing | `scipy.stats`, `statsmodels` |
| Development | Jupyter Notebook |

---

## Analysis Workflow

### 1. **Univariate Analysis**
Explored distribution of individual variables using:
- **Count Plots** to show frequency
- **Pie Charts** to show percentage share

This helped understand:
- Balance of experiment groups
- Base conversion levels
- Ad exposure patterns by day

### 2. **Bivariate Analysis**
Examined relationships between variables, particularly:
- Conversion rate difference between `ad` vs `psa` groups
- Effect of ad exposure on likelihood to convert

### 3. **Statistical Testing**
To determine if the observed conversion difference is **statistically significant**, we tested:

| Hypothesis | Explanation |
|----------|-------------|
| **H₀ (Null)** | There is no difference in conversion rates between groups. |
| **H₁ (Alternative)** | Users in the advertisement group convert more. |

Because normality assumptions were not met:
- **Mann–Whitney U Test** was used.
- Result: **p-value < 0.05**

✅ **Conclusion:** Reject H₀ → Ads **significantly increased conversions**.

---

## Visualizations

### Test Group Distribution
![Test Group Count & Pie](https://github.com/Jericho0015/Marketing-A-B-Testing-Analysis/blob/main/Graphs/Test_Group_bar_pie.PNG)

### Conversion Distribution
![Conversion Count](images/converted_count.png)
![Conversion Pie](images/converted_pie.png)

### Most Ads Day Distribution
![Most Ads Day Count](images/most_ads_day_count.png)
![Most Ads Day Pie](images/most_ads_day_pie.png)

---

## ✅ Final Conclusion

- The advertisement campaign **successfully increased user conversions**.
- Statistical testing confirms the difference is **real and not due to chance**.
- The company can expect **positive ROI** by continuing or scaling similar ad strategies.
- Exposure timing insights can be used to **optimize ad scheduling further**.

---

## How to Run the Project

```bash
git clone https://github.com/yourusername/marketing-ab-testing.git
cd marketing-ab-testing
pip install -r requirements.txt
jupyter notebook
