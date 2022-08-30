![Flight Image](https://github.com/GitHub4lrg/Flight_Market_2022/blob/images/Boening%20_777_%20wikimedia.jpg?raw=true)
# Flight Prediction Price 2022

## Index:

- [Scenario](#scenario)
- [Objective](#objective)
- [First Approach](#first-approach)
- [Analysis](#analysis)
-	[Conclusions](#conclusions)
-	[Presentation](#presentation)
-	[Tools Integration](#tools-integration)
 
## Scenario

### The raw Dataframe presented came from the Bureau of Transportation Statistics (BTS) using DB1BMarket data sets that include flights within US for the period of 2021 (all the four Quarters) and 2022 (first Quarter). The Airline Origin and Destination Survey (DB1B) is a 10% sample of airline tickets from reporting carriers collected by the Office of Airline Information of the BTS.

## Objective

### Main goal is to predict ticket prices for futures flights across all States using provided data, and also present whether distances have a major influence on those prices or not.

## First Approach

### Raw dataset provided consists of records of 28,358,746 flights information for data including the four quarters of 2021, and 1st quarter of 2022. Dataframe at first was handled through different process with the idea of reducing its size to a more managable data, and that included:
- Import and concatenate all data sets.
- Exploratory Data Analysis.
- Data wrangling.
- Data cleaning.
### Going through all mentioned process we had to reset indexes, drop unnecesary columns, readjust columns due to the fact that some itineraries included 1 stop and those were not significant for the scope of this project, filtered columns like Passangers where itineraries with less than 5 represented 78%, same concept for filtering Market Coupons, and the rest of the columns. Data was also check and fixed for null, duplicates, and type values.

### Python was used for this First Approach. To explore our Python Notebook, follow this [link]()

## Analysis

### After finalizing our first approach with the dataset we decided to create three differents dataframes (data1: include only top 5 Origin cities; data2: include only top 5 Origin cities & top 5 Destination cities; df_flight: same as data2 plus only top 7 Carriers); then we started the analysis with the Representation, Evaluation, and Optimization.

- Representation through Machine Learning Algorithm Selection & Implementation.
  - To initiate the analysis in our dataframes (data1, data2, df_flight) we created another Python Notebook, they were pretty cleanned as we checked once again. We iterated one by one doing visual inspection with histograms, barplots, scatterplots, then looked for correlations and patterns while checking distribuition of the data and using describe method. Consequently, some features were dropped, others changed data types, and looking for outliers confirmed some data needed to be transformed for getting it ready for the next steps.
  - Evaluation process requires we separated our target(TicketPrice) from our features, and once separated split features into numerical and categorical data. Numericals were scaled and categoricals encoded to be able to build our linear regression, and KNN model. Our next step was to get our train and test sets to later build an run our models. Our initial plan was to run 3 different sets for everyone of the 3 data sets (data1, data2, df_flight), however based on preliminary results (very bad scores) we decided to go ahead with the next step in this process.
  - Optimization as planned would be with a different algorithm (RandomForest), at this point it was not a surprise the scores we were getting did not make a significant difference.

### Python was used for this Analysis. To explore our Python Notebook, follow this [link]()

## Conclusions

### Results:
 - data1 results:

  - test_size = 0.2, random_state = 50
  - Linear Regression - r2_score (-7288923857373454.0)   mse (1.478487263733959e+20)
  - KNN - r2_score (0.18256172399342874)  n = 60 being the best btw (6 - 100)
  - RandomForestRegressor - no results. After very long time running, had to stop

 - data2 results: It shows better results here, but still not good. Linear regression is not a good algorithm for this df.

  - test_size = 0.2, random_state = 50
  - Linear Regression - r2_score (0.1281434857128746)   mse (26739.778572218645)
  - KNN - r2_score (0.17731027440793024)  n = 40
  - RandomForestRegressor - score (0.15313040002626443)

 - results for df_flight

  - results1: This last df does not reflect big difference, eventhough scores were higher.

   - test_size = 0.2, random_state = 50
   - Linear Regression - r2_score (0.16796755038998035)   mse (27287.71018590392)
   - KNN - r2_score (0.2062641571899162)  n = 40 /  (0.21282696600811746)  n = 60  
   - RandomForestRegressor - score (0.19467609353619353)

  - results2:

   - test_size = 0.4, random_state = 50
   - Linear Regression - r2_score (0.16911968304851277)   mse (27900.26845877992)
   - KNN - r2_score (0.22044850021293194)  n = 60 /  (0.22163268249845014)  n = 80  
   - RandomForestRegressor - score (0.1978057941713265)

### Final thoughs: 
 - The dataframe provided can be used to get some business insight, however it's not enough to reach our main goal of predicting ticket prices for future flights.
 - Prices show an increased value through the different quarters, while demonstrate a decrease value for an increase amount of passangers.
 - Carriers like Frontier and Spirits show around $100 cheaper compare to the other 5 carriers included in our analysis.
 - Finally dataframe shows a marked trend of increased price for an increase in the distance flown.

## Presentation

### We used story in Tableau to make our presentation with the simplest and visually appealing. To view our presentation, follow the [link]().

## Tools Integration

### You can find here access to all the tools we used for this project:

 -	Tableau - Presentation, follow the [link]().
 -	Python - Cleaning/Wrangling, follow the [link]().
 -	Python - ML & Models, follow the [link]().
 -	SQL - Longitud/Latitude coordinates finder, follow the [link]().
