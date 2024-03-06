# London Crime and the Influences of Socio-economic Factors

This was my final project for my MSc Data Science programme

**_Task Description:_** Create a data science project with at least 800 lines of code and a 15,000 word report on a project of your choosing or from the list of suggested projects by supervisors. I decidedto conduct my own project and intitally wanted to look at increasing diversity in the outdoors, however I was unable to use the data in the end so decided to look at crime rates in London based on socio-economic factors instead. 

**_Goal:_** Utilise data analysis and machine learning techniques to:
1. Identify the trends in overall crime between 2011 and 2021 in London and provide
potential explanations.
2. Identify the crimes types that most affected London between 2011 and 2021.
3. Identify the monthly trends in the top 5 major crime types that affected London
between 2011 and 2021.
4. Identify the boroughs with the highest and lowest overall crime rates while taking
into account population size.
5. Investigate whether socio-economic factors such as unemployment rate
(percentage), annual income (median), people earning below the London Living
Wage (percentage) and population density by square kilometer are effective in
predicting overall crime in London using machine learning models.

**_Technologies:_** Python, scikit-learn, pandas, numpy, matplotlib, seaborn and Tableau.

**_Method:_** Using open source data from the London Datastore I gathered Recorded Crime: Geographic Breakdown (csv) for 12 different crimes by London borough by mm/yyyy, The Land Area and Population Density, Ward and Borough (csv) for population density by London borough by mm/yyyy , The Employees Earning Below the London Living Wage (LLW) (xls) for % of people erning below the LLW by London borough by mm/yyyy, The Model Based Unemployment Estimates (xls) for uneployment rates by London borough by mm/yyyy, Earnings by Workplace, Borough (xls) for data on workplace based annual median earnings by London borough by mm/yyyy. 

These datasets were then checked, missing values were imputed or columns/rows dropped, duplicates were removed, column names were standardised, datasets were reshaped and merged by borough and date then aggregated by various combinations of borough, year, month etc for analysis. Feature engineering was conducted to gain crime rates by borough which took into consideration borough population size. Exploratory data analysis was conducted looking at descriptive statistics, visulisations including histograms, boxplots, heatmaps and scatterplots to observe distribution, outliers and correlations. Copies of the data were created with normalisation and without normalisation and with outliers included and with outliers (outliers appeared to be genuine high or low data crime rates) removed to observe the difference in model perfromances. Feature selection was used such as K Select best to observe which socio-economic factors were thought to be most important in predicting crime rates. 

Data was then turned into an array using numpy, data was then split into 80% training data and 20% test data. Predictive models such as Random Forest Regressor and Support Vector Regression were used to try to predict crime rate in London using the socio-economic factors (multiple linear regression was also observed but not used as the assumptions were not met). Numerous model experimentations (hyperparameter tuning) and evaluations then took place on the training data using cross validation. The evaluation metrics used were MSE, MAE, RMSE, R2, MBD and a learning curve visualisation. The final models were then tested on the test data with the best performing model being the Random Forest Regressor on the data with outliers removed explaining 80.4% of variance in London crime rates. The hyperparameters were: n_estimators = 100, max_depth = 10, min_samples_leaf = 2, max_leaf_nodes = 10. Random Forest Regressors feature importance graph suggested that population density contributed the most to predicting Lodnon crime rate, followed by median income.

**_Outcome:_** A 15,000 word academic journal article written in Latex for my MSc Data Science final project, I recieved a high distinction (76%).

**_Improvements:_** Due to time contraints I was only able to look at overall crime rates in London but to further improve this project I would look at the influence that soci-economic factors play on specific crimes in London and I would try to find more open source socio-economic factor data measuring things like inequality and average household income. I also think it would be interesting to observe the effects of weather on crime rates. Furthermore, I would break up the code into different notebooks such as cleaning and processing, exploratory analysis, models etc rather than one long notebook of code to make it easier for others to read.
