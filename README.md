# Pyth-on-the-Border: A Data View of US Immigration Metrics

# US_Southern_Border_Metrics
A interactive GeoCord Map with a list of Checkpoints and Sector locations on an interacive Folium map that can be localized or drag-and-dropped into a web browser along with data analytics of the Immigration metrics throughout the US Southern Border.

# SPC Brandon Cooke, USARMY

![logo](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/fd3cd47c-0dcc-4a0e-b228-9afabc9d0b88)

Data was derrived from the US Customs and Broder Protection Agency.
About CBP
With more than 60,000 employees, U.S. Customs and Border Protection, CBP, is one of the world's largest law enforcement organizations and is charged with keeping terrorists and their weapons out of the U.S. while facilitating lawful international travel and trade.

As the United States’ first unified border entity, CBP takes a comprehensive approach to border management and control, combining customs, immigration, border security, and agricultural protection into one coordinated and supportive activity.

# Data Description

US Immigration polcies are a big talk of the town recently, and so I was wondering what data or metrics can be used to explain the story of immigration in the US and where the most immigration and apprehension influxes take place in the United States. The dataset came in a big CSV file that had data ranging all the way back to 1925!

<img width="1239" alt="DF before cleaning" src="https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/fa22c5bf-f833-4828-8533-a372d9f57cf1">

Tracking down data to answer my questions was pretty simple, but also hard aty the same time. The Geospatial approach I took to explain my findings took me all over the internet to find the best approach to display my data in a comparable manner.

# Final Capstone Goals
- Explore and find out what the most common types of immigration metrics we see at which border.
- Plot out apprehension data to visualize the data.
- Find out the origin countries of immigration (what countires they are from).
- Display my findings with a Folium map with US southern border, checkpoints and sectors.
- Showcase my general knowlege of Python.

# Data Visualization
I first wanted to see based on the preliminary data I obtained, what the rate of apprehesnions were based on the year. First though, I had to clean the data and pre-process it to make it more readable:

<img width="826" alt="Dataframe post cleaning" src="https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/4bbfdc92-24de-4138-b683-0465413081ee">

After that I am able to do a basic plot to visualize the data:
![1st scatterplot](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/d67727de-9bb3-4446-8ccc-6f9b835cbdc7)
Fig 1. General number of unique columns in the dataset, over time.

From that I can see the rate of immigration, and single that out to understand it better with a temporal line graph to showcase the rate of immigration thoughout the years:
![1st Vewing of Data](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/39e668bd-ce44-4b2a-8c55-3d8e6928945c)
Fig 2. The rate of apprehensions collected (to) the United States in the dataset, over time.

To explore the seasonal componet further, I decided to take a look at when in the year the uptick in apprehensions happen, and plotted that. I made the months based on ammount of data and picked out the changes from that since there was so much data to use.

![Seasonal Analysis of Border Apprehensions(Month)](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/e203aae0-300b-448c-b47a-44770a21265c)
Fig 3. The rate of apprehensions (to) the United States in the dataset, over time (by month).

Looking at this this plot we can see that based on the data provided that the month of July seems to be the peak time that we experience an influx of immigrants or apprehensions to the United States. After seeing this I wanted to see where (what border) people are coming to America from, in essence where the encouters are taking place.

# Top Border Areas People are Immigrating To

So after we visualized the rate of immigration and the steady uptick over the course of years, I wnated to see where or what border these people are being met at. I took a look at certain columns and totaled them out to give me a graph that would explain this:

![Distribution of Apprehensions by Location of Apprehension png(BAR GRAPH)](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/dd7ea021-a6ae-4eed-aee5-64de07c351c7)
Fig 4. Distribution of different border areas and their encounters.

Since plotting this result, we can see overwhelmingly that most apprehensions are seen at the Southwest Border. Once relizing this, we can start to focus on a hypothesis of where or what countries people are coming to the Southwest Border from.

# Hypothesis Testing

Country of Origin Comparison Hypothesis:

Based on the previous graphs and data analysis, I have formed a general hypothesis on this dataset and want to explore it further. Noting how collection of data was only starting to be collected in 2000 to differentiate people from Mexico and Other Countries, I will section off that data to perfrom the tests in a true manner:

    * Null Hypothesis (H0): There is no significant difference in the 
    mean apprehension numbers between individuals from Mexico and those from other countries.

    * Alternative Hypothesis (H1): There is a significant difference in the 
    mean apprehension numbers between individuals from Mexico and those from other countries.
    
To perform a hypothesis test comparing the mean apprehension numbers between individuals from Mexico and those from other countries, I can use either an independent t-test or a Mann-Whitney U test, depending on the distribution of the data and whether the assumptions of the t-test are met.

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/11eb0d1b-050e-4703-a858-0f7bd37dff4f)

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/a40c66c9-e5a9-450f-9d18-98418f0f75a4)
Fig 5 and 6. Display of apprehensions and when they started recording based on countries (charts data not collected for 22- 23).




This graph allows us to see that CBP started taking into account the differnt countries immigrants were coming from, in about 2000. from there were able to see that there was a signifigant rise of apprehension of people who were From Mexico vs From Other Countries.
Since we have some solid data based on these findings, I will be able to preform my hypotesis testing.

Here we will compile an Independent T-Test:
<img width="1405" alt="Screenshot 2024-04-30 at 12 53 19 PM" src="https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/cc7ef264-c4b3-4345-9c8a-9a473fde0860">
Fig 7. Overview of Code that compiles Independant T-Test

With a p-value of 0.0099, which is less than the significance level (typically 0.05), we reject the null hypothesis. Therefore, there is sufficient evidence to conclude that there is a significant difference in the mean apprehension numbers between individuals from Mexico and those from other countries.

Since the independent t-test already yielded a significant result, there may not be a strict necessity to perform the Mann-Whitney U test. However, conducting both tests provides a comprehensive analysis and ensures the reliability of the conclusion.

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/5b610c82-2bb1-4740-b43b-5016358fedde)
Fig 8. Overview of Code that compiles Mann-Whitney Test

Providing both data tests, previous data anylysis and plot, we can indeed confirm the Alternate Hypothesis (H1) and reject the Null Hypothesis. Alternative Hypothesis (H1): There is a significant difference in the mean apprehension numbers between individuals from Mexico and those from other countries proves to be true.

# Predictive Forcasting

Upon solving the hypothesis question, I tried to focus on a new topic of pyhton that ive never dabbled in before. After doing some research and back and forth model checking, I settled on a few different models to express predictive trend analysis for this dataset. 

The first model was the SARIMA model:

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/07a88bfe-7902-4c60-9bd5-79fa3f7c86de)
Fig 9. SARIMA Model that predicts based on training data, an uptick in apprehensions.

* Mean Absolute Error (MAE): 1004009.8853928152
* Mean Squared Error (MSE): 1386518719472.697
* Root Mean Squared Error (RMSE): 1177505.2948809601

The SARIMA (Seasonal Autoregressive Integrated Moving Average) model is a time series forecasting model that extends the ARIMA model to account for seasonality in the data. It is particularly useful when dealing with time series data that exhibit periodic patterns or seasonal fluctuations. Overall, using a SARIMA model for the time series data on border apprehensions can capture and model the seasonal patterns, improve forecasting accuracy, and gain insights into the factors influencing changes in apprehension trends over time. After testing the ARIMA model, the SARIMA model ended up being a better represntation of the dataset and predictions.

The second model I took a look at was the Auto ARIMA model. 

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/4fb33aa0-b7fc-4abf-a7af-61ecef466141)
Fig 10. Auto ARIMA Model that forecasts a projection of predicted apprehensions.

* Mean Absolute Error (MAE): 493348.7
* Mean Squared Error (MSE): 335351761941.1
* Root Mean Squared Error (RMSE): 579095.6414454351

The Auto ARIMA, or automated AutoRegressive Integrated Moving Average, is a statistical algorithm that automatically selects the optimal parameters for an ARIMA model. ARIMA models are commonly used for time series forecasting. The problem I was having with the orginal ARIMA model was that it couldnt compensate for the fact trhat the dataset did not have a built in seasonality in the date configuration. When trying to spoof it, and create one for the timeseries data, the model could not process, and was drasticly off course. In summary, Auto ARIMA automates the process of selecting the best ARIMA model for time series data, including both non-seasonal and seasonal components, thereby simplifying the forecasting process and potentially improving forecast accuracy.

The next model I wanted to look at was the ETS model:

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/5dd05e14-0b40-4201-9a6e-f1da80b084dc)
Fig 11. ETS Forecasting Model on potential future border apprehensions.

* Mean Forecast: 2173135.5970056877
* Median Forecast: 2187500.9666306
* Mode Forecast: 1479.0202725556537

The ETS (Error, Trend, Seasonality) model serves the purpose of forecasting future values based on historical data of border apprehensions. The primary function of the ETS model is to provide forecasts for future time periods. By fitting the model to historical data, it captures patterns in the data such as trend and seasonality and uses them to make predictions about future values. This model seemed to work best when it came to predictions, and although I was only able to test it with one dataset for only a small ammount of time, I would be encouraged to use it to develop further analaysis with more data.

The last model I wanted to look at was a Linear Regression Model:

![image](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/8462e6e3-c11a-4d73-954f-31d69c487cc2)
Fig 12. Linear Regression Model making a prediction on increased apprehensions.

* Mean Absolute Error (MAE): 765742.4266966846
* Mean Squared Error (MSE): 744536226995.5281
* Root Mean Squared Error (RMSE): 862865.1267698377

Here is a linear regression model. Linear regression is a statistical method used to model the relationship between a dependent variable (in this case, 'Border apprehensions (People)') and one or more independent variables (in this case, the years). In this specific implementation, the linear regression model is being used to predict the number of border apprehensions based on the year. The independent variable is the year, extracted from the datetime index, and the dependent variable is the number of border apprehensions. The linear regression model assumes a linear relationship between the independent and dependent variables. It estimates the coefficients of the linear equation that best fits the observed data points, allowing us to predict the dependent variable's value based on the independent variable(s). Overall, the model appears to be a reasonable fit for the data. However, it's important to keep in mind that the adequacy of this model depends on the specific context and the goals of the analysis taking place. Additionally, it would be a good practice to try to validate the model on independent/ different datasets and perform additional checks to ensure its robustness. Essentially using other datasest in teh same manner to generate the "same" results when ran. 

# Roundup and Findings

I think I can summarize my findings in a few points,

- There is a significant increase in apprehensions taken at the Southwest Border to the United States.
- There is a overwhelming ammount of more people coming from Mexico vs other countires based on the data.
- There is a positive correlation between the years and the number of border apprehensions. This indicates that, on average, as the years increase, the number of border apprehensions also tends to increase. However, the correlation is not perfect, suggesting that other factors besides time may also influence border apprehensions.
- Prediction of increased immigration is in one sense easy to "predict' but also hard to get "accurate".
  Several key moments, legislation, and factors have influenced fluctuations in U.S. immigration levels over the years:
  * Immigration Act of 1965
  * Refugee Act of 1980
  * Immigration Reform and Control Act of 1986 (IRCA)
  * North American Free Trade Agreement (NAFTA)
  * September 11, 2001, Attacks
  * Deferred Action for Childhood Arrivals (DACA)
  * Trump Administration Policies
  * COVID-19 Pandemic
These are just a few examples of key moments, legislation, and factors that have influenced fluctuations in U.S. immigration levels over time. Immigration trends are influenced by a complex interplay of economic, social, political, and global factors, and they continue to evolve in response to changing circumstances and policies.

Trying to predict a future rate of immigration would be complex in itself to show an "accurate" representation of the data unless we can sumize and actually have hard data points on these events or policies. I would also require more time to compile that data and make it readable by data analysis.

# Additional Capstone MVP

For all the graphs and data analysis that was done to the data, I wanted to be able to show an actual representation of where these apprehensions took place. My MVP would be a Geographic Folium Map that shows the 


