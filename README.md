# DSA210-Term Project: The Impact of Inflation and Exchange Rates on Grocery Prices in Turkey

## Motivation
Purchasing power in Türkiye has fallen significantly in the last five years.
Especially in the last 5 years, Turkey has experienced many difficulties in shaping the cost of living due to high inflation and variable exchange rates. Grocery prices, a basic aspect of daily expenses, are one of the issues that reflect this difficulty. Therefore, this project aims to analyze the relationship between inflation, exchange rates, and grocery prices in Turkey and to observe the impact of these changes on consumers.

---

## Goal

The goals I want to achieve at the end of this project are to understand how inflation and currency depreciation affect market prices, by examining historical data and applying data science techniques, this study will understand to what extent macroeconomic variables affect food prices and observe situations that will benefit the consumer.

---

## Objectives
Analyze historical trends
- Analyze throughout the last years the trends in inflation, variations in exchange rates, and food pricing adjustments.
- List major times of significant inflation and devaluation of currencies and how these affected food costs.

Analyze the impact of changing exchange rates:
- Find out how imported food product pricing change with declining Turkish Lira value.
- Consider the price sensitivity of supermarket products imported from abroad against those made locally.
   
Determine how inflation affects grocery prices.
- Calculate the relationship between supermarket pricing hikes and overall inflation rates.
- Find whether food prices rise faster than general inflation.

---

## Hypothesis 
**H₀(Null Hypothesis):** Grocery prices are significantly influenced by inflation and changes in exchange rates; higher inflation and devaluation of currencies drive higher food prices. 

**Hₐ(Alternative Hypothesis):** Grocery prices in Turkey are not statistically significantly influenced by inflation or trade policies.

---

## Data Analysis Approach
**Data Collection & Cleaning** 

Gather historical data from;
- **Central Bank of Turkey (CBRT):** Historical exchange rate data (USD/TRY, EUR/TRY).

- **Turkish Statistical Institute (TÜİK) and International Monetary Fund:** Monthly inflation rates, consumer price index (CPI), and grocery price index.

- **International Organizations (IMF, World Bank):** Global food price indices for comparison.

Handle missing values, eliminate contradictions, and standardize data to ensure validity.

Organize time-series data such that it is ready for study.

**Exploratory Data Analysis (EDA)**
- Summarize important trends using descriptive statistical analysis.

- Find links among grocery prices, inflation, and exchange rates.

- Analyze past trends in price swings following changes in exchange rates or a recession.

- See long-term trends using moving averages and trend analysis.

**Hypothesis Testing**
- Use statistical tests to support hypotheses.

- Analyze the correlations among grocery prices, exchange rates, and inflation.

- Regression Modeling: Evaluate food price changes and the strength and relevance of inflation and currency rates.

- Analyze the importance of findings depending on confidence intervals and p-values.

**Visualization and Interpretation**
- Use time series graphs, heatmaps, and scatter plots to investigate the relationships between variables.
- For detailed examination, it is highly recommended to check the following: [Findings](DSA210_projectcode.ipynb)

---

## **Findings**
**Data Collection:** Through April 2020, data were collected from the Central Bank of Turkey (CBRT) and Turkish Statistical Institute (TÜİK), and the International Monetary Fund

**Dataset:**
- Date: Dates are noted to be evaluated individually every month.
- US dollar effective sale:
- Consumer Price Index (General):
- Consumer Price Index (Food and Beverages):

**Data Processing:**

**1. Data Cleaning**
- Converting the date column to a datetime format and setting it as an index
- Rename the column names for easy reading

**2. Data Visualization**
  
   - Trends Over Time Line Plot:
      - This graph depicts the historical development of General CPI and Food CPI.
      - Both measures show a definite upward trend, suggesting ongoing inflation.
      - It helps visually verify that general consumer prices and food costs have risen significantly over the years.
   - Scatter Plots with Regression Lines
      - General CIP vs USD
         - This scatter plot shows the general inflation in connection with the currency rate (USD).
         - The fitted regression line indicates a strong positive linear correlation: overall CPI tends to rise when the value of the dollar rises.
      - Food CIP vs USD
         - This graph analyses how exchange rate changes impact food prices.
         - It reveals a comparably strong, positive trend: currency devaluation links to higher food prices.
      - General CIP vs Food CIP
         - This contrast highlights the internal stability of inflation signals.
         - The almost perfect linear correlation supports the notion that food CPI is closely connected to the larger economic price trends by showing that rises in food prices significantly reflect general inflation.
  	
**3. Regression and Correlation Analysis**

- **Simple Linear Regression:**
   - Two separate linear regression models were built to examine how the USD exchange rate affects:
      - General CIP
      - Food CIP 
   - The independent variable in both situations is the USD; the dependent variable is the CPI index—either general or food.
   - The regression model lets us measure the direction and intensity of the association and check its statistical significance.
- **Pearson Correlation Test:**
   - A linear relationship between two continuous numerical variables is evaluated using this test, which examines both the strength and direction of the link.
   - This test helps to answer this question:
      - "Are food prices and general inflation significantly and linearly affected by the USD exchange rate?"
   - Results:
      - r ≈ 0.98 → Very strong positive correlation
      - p-value ≪ 0.05 → The relationship is statistically significant 
- **Correlation Heatmap:**
   - The correlation coefficients between all three factors were shown visually in the form of a heatmap.
   - The color scale from red to blue shows how strong and in what direction the connection is going.
   - There is a strong link between all of the variables:
      - Especially CIP_food and CIP_general (they are almost perfectly linked).
      - This makes the statistical results from the regression and Pearson tests look even stronger.

**4. Hypothesis Testing**

H₀(Null Hypothesis): Grocery prices are significantly influenced by inflation and changes in exchange rates; higher inflation and devaluation of currencies drive higher food prices. 

Hₐ(Alternative Hypothesis): Grocery prices in Turkey are not statistically significantly influenced by inflation or trade policies.
-  Both p-values are smaller than 0.05, so we fail to reject the null hypothesis.
-  Exchange rates have a statistically significant effect on grocery prices in Turkey.
  	








