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
- Oil Prices
- Unemployment Rate: Evaluated quarterly.

**Data Processing:**

**1. Data Cleaning**
- Converting the date column to a datetime format and setting it as an index
- Rename the column names for easy reading

**2. Data Visualization**
  
   - Histograms:
      - USD (Standardized) Distribution
         - The pattern is skewed to the right, with a long tail that points to the upside. This means that the USD was mostly below the average, but there were a few times when it increased significantly.
         - Outliers on the right may show times of currency problems or rapid devaluation.
      - Unemployment Rate (Standardized) Distribution
         - This distribution seems more balanced than USD but is still slightly skewed left.
         - The large range shows that unemployment changes a much over time.
   - Time Series Line Plot:
      - Changes in Standardized Oil Prices Over Time
         - The figure shows a clear upward trend toward the right side.
         - The price changes show that oil prices are unstable, especially during certain times, such as when there are global price shocks or international events.
   - Trends Over Time Line Plot:
      - This graph depicts the historical development of General CPI and Food CPI.
      - Both measures show a definite upward trend, suggesting ongoing inflation.
      - It helps visually verify that general consumer prices and food costs have risen significantly over the years.
   - Scatter Plots
      - Oil Prices vs USD 
         - This is a very strong positive relationship: when oil prices go up, the USD (exchange rate) also goes up.
         - The points go up, which means that energy costs and the USD are very closely tied.
      - Unemployment Rate vs USD
         - This reveals a strong negative relationship: when unemployment goes up, the USD tends to go down.
         - This is intriguing since it goes against what most people think: high unemployment is usually seen with a weak currency.
         - But this could be due to trailing effects or the way the data is set up. For example, periods with increased TL may have been followed by a cooling economy and employment loss.  
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
   - It is used to analyze how the USD exchange rate affects consumer price indices in Turkey.
   - In both models, the independent variable is the standardized USD exchange rate (usd_std), and the dependent variables are the standardized food CPI and general CPI.
   - Results show that the USD has a very strong and statistically significant impact on both food and general consumer prices.
      - For the food CPI model, the R-squared value is 0.948, indicating that about 95% of the variance in food prices is explained by changes in the USD.
      - For the general CPI model, The has an R-squared value is 0.946.   
   - In both cases, the p-values for the USD variable are well below 0.001, confirming the significance of the relationship.
   
- **Pearson Correlation Test:**
   - To further explore the linear relationships, Pearson correlation tests were applied using standardized variables.
   - The correlation between USD and food CPI is approximately 0.985, and between USD and general CPI, it is around 0.983. These values reflect a very strong positive relationship.
   - The correlation between USD and oil prices is also very strong and positive, around 0.987. On the other hand, the correlation between USD and unemployment rate is strongly negative, about -0.946.
   - All of these relationships are statistically significant, with p-values close to zero.
     
- **Correlation Heatmap:**
   - A heatmap was used to visually represent the correlation matrix between the USD, food CPI, and general CPI. The results confirm what the correlation coefficients show: all three variables are strongly linked.
   - In particular, food CPI and general CPI are almost perfectly correlated, supporting the idea that food inflation closely tracks overall inflation trends.
   - The heatmap’s color gradient helps emphasize the strength and direction of these associations.
     
- **Lagged Regression** 
   - To investigate whether macroeconomic indicators from the previous period affect food prices in the current period, a lagged regression was also conducted.
   - In this model, the lagged oil price (Oil_price_lag1) was found to have a strong, positive, and statistically significant effect on food CPI in the following period (p < 0.001).
   - The lagged unemployment rate (Unemployment_lag1) showed a negative coefficient but was not statistically significant (p = 0.429). This suggests that while energy prices from the previous quarter influence current food prices, unemployment may not have an immediate or direct impact.

**4. Hypothesis Testing**

H₀(Null Hypothesis): Grocery prices are significantly influenced by inflation and changes in exchange rates; higher inflation and devaluation of currencies drive higher food prices. 

Hₐ(Alternative Hypothesis): Grocery prices in Turkey are not statistically significantly influenced by inflation or trade policies.
-  Both p-values are smaller than 0.05, so we fail to reject the null hypothesis.
-  Exchange rates have a statistically significant effect on grocery prices in Turkey.

**5.Machine Learning**

- Prophet Modelling
   - Oil Prices
      - 
   - CIP Food
      -  

- K-Means Modelling
   - 









