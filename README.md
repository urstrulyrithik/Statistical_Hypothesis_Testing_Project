# Statistical Hypothesis Testing 🚕✨

Welcome to the NYC Yellow Taxi Data Analysis project! This repository showcases how to clean and analyze real-world taxi data to uncover insights about passenger counts, fare amounts, trip distances, and more.

## Overview 🚦

This project takes the **January 2020 NYC Yellow Taxi Trip Records** and walks through essential steps of data cleaning, exploratory data analysis, and hypothesis testing. Specifically, we compare **fare amounts** between credit card and cash transactions to see if there's a significant difference.

## Table of Contents 🗂

- Features
- Data Cleaning Steps
- Exploratory Analysis
- Statistical Testing
- Business Insights
- Usage
- Technologies

## Features 🎉

- **Data Cleaning:** Removal of duplicates, handling missing values, outlier filtering, and data type conversions.
- **Descriptive Statistics:** Summaries of fare amounts, trip distances, and ride durations.
- **Visualization:** Histograms and pie charts to easily compare **credit** vs. **cash** transactions.
- **T-Test:** Statistical comparison of mean fare amounts to identify significant differences between payment methods.
- **Business Insight:** Suggestions for maximizing revenue based on user payment preferences.

## Data Cleaning Steps 🧹

- **Missing Values:** Approximately 1% of rows contained null values; these were dropped to maintain data integrity.
- **Duplicate Removal:** Found and removed over 3.3 million duplicate rows to prevent skewed results.
- **Type Conversions:** Converted passenger count and payment type from floats to integers where appropriate.
- **Filtering Outliers:** Applied the IQR method to remove extreme values for fare amount, trip distance, and ride duration.
- **Valid Range Filters:**
  - Passenger counts limited to 1 through 5.
  - Removed negative or zero values for fare, distance, and duration.
  - Limited payment type to **Cash** or **Card**.

## Exploratory Analysis 🔎

- **Distribution Analysis:** Visualized histograms for fare amounts and trip distance split by payment type.
- **Descriptive Statistics:** Summary of mean, standard deviation, and counts to get an overview of data spread.
- **Payment Type Preference:** Pie chart indicating the split between **cash** and **card** payments.

## Statistical Testing 📊

I used a **Welch’s T-test** for comparing the means of fare amounts between **card** and **cash** payments because:

- The data does not perfectly follow a normal distribution (as indicated by the QQ plot).
- The population standard deviation is unknown.
- The T-test is robust for both small and large sample sizes.

**Null Hypothesis (H₀):** No difference in the average fare between credit card and cash payments.  
**Alternative Hypothesis (H₁):** There is a difference in the average fare between credit card and cash payments.

**Result:**

- **T-statistic:** ~165.60
- **p-value:** 0.0 (effectively zero)

Since the p-value is much smaller than the usual 5% significance level, we reject the null hypothesis.

## Business Insights 💡

- Credit card transactions show a statistically significant higher average fare compared to cash payments.
- Encouraging **card payments** could potentially boost revenue for taxi drivers or fleet operators.
- Further investigation into why credit card fares tend to be higher (e.g., trip distance, ride duration, or time of day) can inform targeted strategies.

## Usage ⚙️

1. Clone this repository:
   ```bash
   git clone https://github.com/urstrulyrithik/Statistical_Hypothesis_Testing_Project
   ```
2. Install Dependencies:
   ```bash
    pip install pandas matplotlib seaborn scipy statsmodels
   ```
3. Run the Notebook:  
   Open the `.ipynb` notebook in [Jupyter](https://jupyter.org/) to execute the analysis step by step.

4. Explore the Results:  
  Check the console and review the generated plots for detailed statistics and visual insights. The notebook displays the t-test summary, which provides the final conclusions on the fare differences between payment methods.

## Technologies 🛠

- **Python 3.8+**  
- **Pandas** for data manipulation  
- **Matplotlib** and **Seaborn** for visualization  
- **SciPy** for the Welch’s T-test  
- **Statsmodels** for QQ plots

**Thank you for checking out this project!** If you have any questions or suggestions, feel free to open an issue or make a pull request. Happy analyzing! 🚀
