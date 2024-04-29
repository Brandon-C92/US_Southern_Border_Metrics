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

US Immigration polcies are a big talk of the town recently, and so I was wondering what data or metrics can be used to explain the story of immigration in the US and where the most immigration influxes take place in the United States. The dataset came in a big CSV file that had data ranging all the way back to 1925!

<img width="1239" alt="DF before cleaning" src="https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/fa22c5bf-f833-4828-8533-a372d9f57cf1">

Tracking down data to answer my questions was pretty simple, but also hard aty the same time. The Geospatial approach I took to explain my findings took me all over the internet to find the best approach to display my data in a comparable manner.

# Final Capstone Goals
- Explore and find out what the most common types of immigration metrics we see at which border.
- Find out where these immigrants are coming from (what countires they are from).
- Display my findings with a Folium map with border, checkpoints and sectors.
- Showcase my general knowlege of Python

# Data Visualization
I first wanted to see based on the preliminary data I obtained, what the rate of immigration was based on the year. First though, I has to clean the data and pre process it to make it more readable:

<img width="826" alt="Dataframe post cleaning" src="https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/4bbfdc92-24de-4138-b683-0465413081ee">

After that I am able to do a basic plot to visualize the data:
![1st scatterplot](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/d67727de-9bb3-4446-8ccc-6f9b835cbdc7)
Fig 1. General number of unique columns in the dataset, over time.

From that I can see the rate of immigration, and single that out to understand it better with a temporal line graph to showcase the rate of immigration thoughout the years:
![1st Vewing of Data](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/39e668bd-ce44-4b2a-8c55-3d8e6928945c)
Fig 2. The rate of immigration to the United States in the dataset, over time.

To explore the seasonal componet further, I decided to take a look at when in the year might the uptick in immigration happen, and plotted that. I made the months based on ammount of data and picked out the changes from that since there was so much data to use.

![Seasonal Analysis of Border Apprehensions(Month)](https://github.com/Brandon-C92/US_Southern_Border_Metrics/assets/161045627/e203aae0-300b-448c-b47a-44770a21265c)
Fig 3. The rate of immigration to the United States in the dataset, over time (by month).

Looking at this this plot we can see that based on the data provided that the month of July seems to be the peak time that we experience an influx of immigrants to the United States.
