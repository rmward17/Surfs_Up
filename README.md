# Surfs_Up
## Overview of the analysis: 
### Purpose
W. Avy is looking to invest in my surf and ice cream shop. In order to convine him, I had to do a climate analysis on a sqlite file he provided. He liked the analyis but  wants more information about temperature trends before giving me the okay to open the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu, in order to determine if my business will be sustainable year-round.

### Analyis
Since the weather data is in a sqlite file, I was able to use SQLAlchemy to query the data and use pandas dataframes to investigate the data. In doing so, I was able to get the summary statistics and create a plot of the precipitation data from the last year.

![Prcp_Last_Year](https://github.com/rmward17/Surfs_Up/blob/main/Prcp_Last_Year.png)

![Prcp_Last_Year_Summ_Stats](https://github.com/rmward17/Surfs_Up/blob/main/Last_year_summ_stats.png)

There are 9 station on the island that record temperature data. Using the code below, I was able to determine the most active station on the island and get the temperature observation data for the last 12 months from that station.

    #queries the stations, the number of records from each station, 
    #groups the counts by the station, and orders the results in descending order
    session.query(Measurement.station, func.count(Measurement.station)).\
      group_by(Measurement.station).order_by(Measurement.station.desc()).all()

Below is a plot of the temperautre data mentioned above.

![most_active_station_temps_plot](https://github.com/rmward17/Surfs_Up/blob/main/most_active_station_temps_plot.png)

W. Avy also wanted specific queries for the temperatures for the months of June and December. Below are their summary statisics. 

June        |  December
:-------------------------:|:-------------------------:
![June Temps](https://github.com/rmward17/Surfs_Up/blob/main/June_Temp_Stats.png)|![December Temps](https://github.com/rmward17/Surfs_Up/blob/main/Dec_Temp_Stats.png)

## Results: 
Using the queries above, I have determined a few things:
- The average June Temperature is ~75 degrees. This is a great temperaure for surfing since it is just warm enough that the ice cream will be refreshing while being cool enough that the sun reflecting off of the ocean won't make the surfers too hot to go out on the water.
- The average December Temperature is ~71 degrees. This is very important as it shows that in the summer and winter, the temerpature doesn't vary that much which means surfing and ice cream will be popular all year-round.
- The data covrs the years 2010-2017. This provides us with a very large sample size which means that we have a very good idea of what will most likely happen when we open our shop. However, it would be best to include more recent data or major storm data becuase one unusual year could wipe out our business.
## Summary: 
In conclusion, we can see that the temperature is ideal for the shop all year round. Additionally, I wanted to get a better idea about the percipitation year round. To that, I queried the percepitation data for June and December. Based on the summary statistics below, you can see that it doen't rain heavily very often. This is also ideal for the surf shop! This means that people will be out and about at all times of the year, surfing and wanting ice cream. 

June        |  December
:-------------------------:|:-------------------------:
![June Prcp](https://github.com/rmward17/Surfs_Up/blob/main/June_Prcp_Stats.png)|![December Prcp](https://github.com/rmward17/Surfs_Up/blob/main/Dec_Prcp_Stats.png)

As we continue this process, I would like to do these queries for a few other months throughout the year to get an understanding of the year as a whole. I look forward to working with W. Avy and opening my shop!
