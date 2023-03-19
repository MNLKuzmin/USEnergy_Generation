# Phase 4 Project
## USEnergy_Generation
Student name: Maria Kuzmin
Student pace: Flex
Scheduled project review date/time: Tuesday, March 21st 10AM
Instructor name: Morgan Jones
## Time Series Model:

### Business Problem:

Electrical Energy is constantly in more demand. 
<br>With technology advancing and broadening applications in different fields there are always more industries heavily depending on significant amounts of electricity.
<br>A few examples of these industries are data centers, hospitals & healthcare facilities, warehouses & distribution centers, and the list goes on (for more details on this you can read [this article](https://www.globalpwr.com/top-ten-industries-requiring-megawatts-of-generator-power/)). 
<br>Whether you want to invest in the energy sector and are looking into what type of source for power you should focus on, or if you are looking to start a massive Cloud service, and wondering where is the most efficient location to have your data servers built and run, or you want to invest in a hospital or a warehouse, this project aims at helping you understand what energy source and state within the United States, is best for you. 
<br>We are going to study the different sources of energy and how their production has been growing or decreasing in the past 20 years. Ultimately we will try to identify what would be the most reliable source of energy to focus on. 
<br>We will then try to predict the production via that source for the next 3 years. <br>Consequently we will look at what are the states that have been the greatest productors, and what is the seasonal pattern in those states.

### Summary:
    
We studied the production of electrical energy in the United States, from 2001 until May 2022.
<br>The data has information on the energy produced, with one record per month, divided by sources and by state.
<br>The dataset consists of 496774 rows × 6 columns. This seemed like an appropriate amount of data, giving us a chance to dig deeper into certain aspects like source or state, and had information that was very recent, going all the way up to 2022 making our future predictions relevant and interesting.
<br>We decided to focus on the production of electricty via natural gas, as that showed a promising positive trend.

Data Preparation: we organized the data by date, studied it in terms of the production in all of the US, and also separated by state.
The libraries used:
- Pandas was used for parsing the data to a date format and working with DataFrames and Series. It seemed a good choice since it allowed us to read the file, create a DataFrame and parse the date, all in one line of code.
- NumPy for basic math and statistic operations.
- SciPy to run an analysis on our data samples, to make sure there were no particular anomalies in the data.
- Sklearn in order to do a time series split, which we used for a cross validation.

For modeling we used statsmodels.
<br>We decided to create a few ARMA models and later run a gridsearch to find the best parameters.
<br>Consequently we used SARIMAX to add the seasonal aspect to our models, and ran two grid searches to find the best performing model.
<br>To compare the models and pick the best ones we used a cross-validation on a split we made from the train set. The best model we picked had an AIC of 173.5.
<br>With this model we made predictions on the test set, for a span of 51 months, and obtained predictions with a RMSE of 10.9 TWh.
<br>We forecasted our data in the future for 3 years, and obtained results with a MSE between 5-9 TWh, finding a growth of up to 16.4%.
<br>We studied also the production of natural nas by state and studied the seasonality of the time series.
