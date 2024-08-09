# CapstoneProject
Final Capstone on Gold Price prediction and US uncertainity Index
Goal of the Capstone project is to predict Gold Prce and factors inflencing Gold price along with impact of economic uncertainity index.

### Price prediction model for Gold based on time-series data, US Uncertainity Index, US Volatility Index, Oil Volatility Index and a standalone model using Twitter feed on Gold Price

**Prasanna Nippani**

#### Executive summary

**Project overview and goals:** The goal of this project is to create ML models to predict Gold Price based on historical Time-series data along with finding correlations with potential influencers. For the projects, I will be training and tuning seven different models to predict/forecast gold price. The six approaches are: 
1. ARIMA
2. SARIMAX
3. Deep Neural networks
   a). LSTM <br />
   b). GRU<br />
5. Correlations between Gold time series and various uncertainities
    a. Economic Policy Uncertainty Index for United States <br />
    b. Equity Market-related Economic Uncertainty Index <br />
    c. CBOE Volatility Index <br />
    d. CBOE Gold ETF Volatility Index<br />
    e. CBOE Crude Oil ETF Volatility Index<br />
6. Correlations between different time series data using linregress
7. Gold news Tweet Callsification NLP models
    a. naive bayes model with tfidf vectorizer __
    b. Logistic Regression model with tfidf vectorizer __
    c. SVC model with tfidf vectorizer__


**Findings:** The best forecast was found to be SARIMAX model, although deep Neural network LTSM models did as well with very low MSE of ~300. Clearly for timeseries data, ARIMA and SARIMAX demonstrated better predictions. As for the correlations between Gold price and various factors, Logistic Regression model suggested "Economic Policy Uncertainty Index for United States - USEPUINDXD" had the highest  correlation of 0.35, followed by "Equity Market-related Economic Uncertainty Index -WLEMUINDXD" of 0.31. The other three indexes namely "CBOE Volatility Index- VIXCLS", "CBOE Gold ETF Volatility Index- GVZCLS" and "CBOE Crude Oil ETF Volatility Index-OVXCLS" had equally influence with correlation of 0.28.

The correlations between all the uncertainity indexes and Gold price/Volume was calcaulated using linregress. Following three indexes 'VIXCLS','OVXCLS','GVZCLS' had equally coefficient value of 3243.77 and the coefficient for USEPUINDXD (Economic Policy Uncertainty Index for United States) index came out to be 50.21 while Equity Market-related Economic Uncertainty Index -WLEMUINDXD had a negative coefficient of -232.514.

Fianlly, for NLP based GOLD news tweet analysis, Logistic Regression had the best accuracy score with 0.79 F1 value.



**Results and conclusion:** The evaluation of the best model was with SARIMAX along with deep neural network LTSM model was found to be the best way to forecast Gold Prices.

#### Rationale
The rationale for this project is to build various ML models to help predict gold price considering various influencing factors.

#### Research Question
What's the best model to predict Gold Price and identify correlation and coffiecients for various volatility and indexes.  

#### Data Sources
The following data sources were used for this project.
Data citations:
---Market Yield on U.S. Treasury Securities at 10-Year Constant Maturity, Quoted on an Investment Basis

https://fred.stlouisfed.org/series/DGS10
Treasury data :Board of Governors of the Federal Reserve System (US), Market Yield on U.S. Treasury Securities at 10-Year Constant Maturity, Quoted on an Investment Basis [DGS10], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/DGS10, July 2, 2024.


---10-Year Breakeven Inflation Rate (T10YIE)
https://fred.stlouisfed.org/series/T10YIE

---- Economic Policy Uncertainty Index for United States 
The daily news-based Economic Policy Uncertainty Index is based on newspapers in the United States.

https://fred.stlouisfed.org/series/USEPUINDXD
Suggested Citation:
Baker, Scott R., Bloom, Nick and Davis, Stephen J., Economic Policy Uncertainty Index for United States [USEPUINDXD], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/USEPUINDXD, July 2, 2024.


---Global Economic Policy Uncertainty Index: Current Price Adjusted GDP (GEPUCURRENT)
https://fred.stlouisfed.org/series/GEPUCURRENT
The Global Economic Policy Uncertainty Index is a GDP-weighted average of national EPU indices for 20 countries: Australia, Brazil, Canada, Chile, China, France, Germany, Greece, India, Ireland, Italy, Japan, Mexico, the Netherlands, Russia, South Korea, Spain, Sweden, the United Kingdom, and the United States..
Suggested Citation:
Baker, Scott R., Bloom, Nick and Davis, Stephen J., Global Economic Policy Uncertainty Index: Current Price Adjusted GDP [GEPUCURRENT], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/GEPUCURRENT, June 27, 2024.


---Equity Market-related Economic Uncertainty Index (WLEMUINDXD)
https://fred.stlouisfed.org/series/WLEMUINDXD
For additional details, including an analysis of the performance of the model, see Baker, Scott, Nicholas Bloom and Steven Davis (2012), "Measuring Economic Policy Uncertainty"

Suggested Citation:
Baker, Scott R., Bloom, Nick and Davis, Stephen J., Equity Market-related Economic Uncertainty Index [WLEMUINDXD], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/WLEMUINDXD, July 2, 2024.

---CBOE Volatility Index: VIX (VIXCLS)
https://fred.stlouisfed.org/series/VIXCLS
VIX measures market expectation of near term volatility conveyed by stock index option prices. Copyright, 2016, Chicago Board Options Exchange, Inc. Reprinted with permission.

Suggested Citation:
Chicago Board Options Exchange, CBOE Volatility Index: VIX [VIXCLS], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/VIXCLS, July 2, 2024.

---CBOE Gold ETF Volatility Index (GVZCLS)
Exchange Traded Funds (ETFs) are shares of trusts that hold portfolios of stocks designed to closely track the price performance and yield of specific indices. Copyright, 2016, Chicago Board Options Exchange, Inc. Reprinted with permission.

Suggested Citation:
Chicago Board Options Exchange, CBOE Gold ETF Volatility Index [GVZCLS], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/GVZCLS, July 2, 2024.

--- OIL
CBOE Crude Oil ETF Volatility Index (OVXCLS)
https://fred.stlouisfed.org/series/OVXCLS
Exchange Traded Funds (ETFs) are shares of trusts that hold portfolios of stocks designed to closely track the price performance and yield of specific indices. Copyright, 2016, Chicago Board Options Exchange, Inc. Reprinted with permission.

Suggested Citation:
Chicago Board Options Exchange, CBOE Crude Oil ETF Volatility Index [OVXCLS], retrieved from FRED, Federal Reserve Bank of St. Louis; https://fred.stlouisfed.org/series/OVXCLS, July 2, 2024.


#### Methodology
Holdout cross validation was implemented. Models were trained on the training set and validated with the test set. Additionally, RandomizedSearchCV was used to evaluate models using accuracy score, and fine tuned each model's hyperparameters to maximize this metric.


#### Next steps
Next steps can include a consolidatation of all the 7 models and creating a forecasting approach that rationalizes output from all the models along with the baility to listen to real-time tweet info that affects/influences Gold price. 

#### Outline of project

- [Link to notebook 1]()



##### Contact and Further Information
# CapstoneProject
Final Capstone on Gold Price prediction and US uncertainity Index
Goal of the Capstone project is to predict Gold Prce and factors inflencing Gold price along with impact of economic uncertainity index.
