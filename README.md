![Flight Image](https://github.com/GitHub4lrg/Flight_Market_2022/blob/main/images/Boening%20_777_%20wikimedia.jpg)
# Flight Prediction Price 2022

## Index:

- [Scenario](#scenario)
- [Objective](#objective)
- [First Approach](#first-approach)
- [Analysis](#analysis)
-	[Conclusions](#conclusions)
-	[Presentation](#presentation)
-	[Contact](#contact)

## Scenario

The raw Dataframe presented came from the Bureau of Transportation Statistics (BTS) using DB1BMarket data sets that include flights within US for the period of 2021 (all four quarters) and 2022 (first quarter). The Airline Origin and Destination Survey (DB1B) is a 10% sample of airline tickets from reporting carriers collected by the BTS's Office of Airline Information.

## Objective

The main goal is to predict ticket prices for futures flights across all states using the provided data, and also present whether distances have a major influence on those prices or not.

## First Approach

The raw dataset provided consists of information for 28,358,746 recorded flights, including all four quarters of 2021, and the 1st quarter of 2022. The dataframe at first was handled through different processes with the idea of reducing its size to a more managable. The processes included:
- Import and concatenate all data sets.
- Exploratory Data Analysis.
- Data wrangling.
- Data cleaning.
Going through all the mentioned processes we had to reset indexes, drop unnecesary columns, readjust columns due to the fact that some itineraries included 1 stop and those were not significant for the scope of this project, filtered columns like Passangers where itineraries with less than 5 represented 78%. We used the same concept for filtering Market Coupons and the rest of the columns. Data was also checked and fixed for null, duplicate, and type values.

Python was used for this First Approach. To explore our Python Notebook, follow this [link](Python/Flight_Market_2022.ipynb)

## Analysis

After finalizing our first approach with the dataset we decided to create three differents dataframes (data1: includes only top 5 Origin cities; data2: includes only top 5 Origin cities & top 5 Destination cities; df_flight: same as data2 plus only top 7 Carriers); we then started the analysis with the Representation, Evaluation, and Optimization.

- Representation through Machine Learning Algorithm Selection & Implementation.
  - To initiate the analysis in our dataframes (data1, data2, df_flight) we created another Python Notebook, these were already pretty cleaned. We iterated one by one doing visual inspection with histograms, barplots, scatterplots. Afterwords, we looked for correlations and patterns while checking distribuition of the data and using the described method. Consequently, some features were dropped, others changed data types, and we looked for outliers to confirm some data needed to be transformed to get it ready for the next steps.
  - The evaluation process requires us to separate our target(TicketPrice) from our features, and once separated split features into numerical and categorical data. Numericals were scaled and categoricals encoded to build our linear regression, and KNN model. Our next step was to get our train and test sets to later build an run our models. Our initial plan was to run 3 different sets for every one of the 3 data sets (data1, data2, df_flight), however based on preliminary results (very bad scores) we decided to go ahead with the next step in this process.
  - Optimization as planned would be completed with a different algorithm (RandomForest), at this point it was not a surprise the scores we were getting did not make a significant difference.

Python was used for this Analysis. To explore our Python Notebook, follow this [link](Python/Flight_Market_2022B.ipynb)

## Conclusions

Results:

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

Final thoughs: 
 - The dataframe provided can be used to get some business insight, however it's not enough to reach our main goal of predicting ticket prices for future flights.
 - Prices show an increased value through the different quarters, while demonstrating a decreased value for an increased amount of passangers.
 - Carriers like Frontier and Spirit are around $100 cheaper compared to the other 5 carriers included in our analysis.
 - Finally dataframe shows a marked trend of increased price for an increase in the distance flown.

## Presentation

We used story in Tableau to make our presentation with the simplest and visually appealing tools. To view our presentation, follow the [link]([https://public.tableau.com/views/FlightMarket2022/Dashboard1?:language=en-US&:display_count=n&:origin=viz_share_link](https://public.tableau.com/views/FlightMarket2022/FlightMarketPrice2022?:language=en-US&:display_count=n&:origin=viz_share_link)).

## Contact
Luis R Guerrero - @lrgutube09 - lrgutube09@gmail.com

Project Link: https://github.com/GitHub4lrg/Flight_Market_2022
