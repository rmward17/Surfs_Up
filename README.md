# Surfs_Up
## Overview of the analysis: 
### Purpose
W. Avy is looking to invest in my surf and ice cream shop. In order to convine him, I had to do a climate analysis on a sqlite file he provided. He liked the analyis but  wants more information about temperature trends before giving me the okay to open the surf shop. Specifically, he wants temperature data for the months of June and December in Oahu, in order to determine if my business will be sustainable year-round.

### Analyis
Since the weather data is in a sqlite file, I was able to use SQLAlchemy to query the data and use pandas dataframes to investigate the data. In doing so, I was able to get the summary statistics and create a plot of the precipitation data from the last year.

- insert image of first plot
- insert image of summ stats

There are 9 station on the island that record temperature data. Using the code below, I was able to determine the most active station on the island and get the temperature observation data for the last 12 months from that station.

    #queries the stations, the number of records from each station, 
    #groups the counts by the station, and orders the results in descending order
    session.query(Measurement.station, func.count(Measurement.station)).\
      group_by(Measurement.station).order_by(Measurement.station.desc()).all()

Below is a plot of the temperautre data mentioned above.

- insert plot

W. Avy also wanted specific queries for the temperatures for the months of June and December. Below are their summary statisics. 

- Summary Stats

## Results: 
Provide a bulleted list with three major points from the two analysis deliverables. Use images as support where needed.

Using the queries above, I have determined a few things:
- The average June Temperature is ~75 degrees. This is a great temperaure for surfing since it is just warm enough that the ice cream will be refreshing while being cool enough that the sun reflecting off of the ocean won't make the surfers too hot to go out on the water.
- The average December Temperature is ~71 degrees. This is very important as it shows that in the summer and winter, the temerpature doesn't vary that much which means surfing and ice cream will be popular all year-round.
- There
## Summary: 
Provide a high-level summary of the results and two additional queries that you would perform to gather more weather data for June and December.
