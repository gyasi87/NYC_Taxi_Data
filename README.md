# NY City Taxi Fare Prediction Exploration using Dask

This is data on New York City Taxi rides The Dataset is published by NYC and there are over 15 million trips. Our dataset includes every taxi ride in the city of New York in the year of 2015, including when and where it started and stopped, a breakdown of the fare, etc.
The data is from [here](https://www.kaggle.com/kentonnlp/2014-new-york-city-taxi-trips?select=nyc_taxi_data_2014.csv).

 Features that are included in the dataset:
- vendor_id - str
- fare_amount - float dollar amount of the cost of the taxi ride
- pickup_datetime - timestamp value indicating when the taxi ride started.
- dropoff_datetime - timestamp value indicating when the taxi ride ended.
- pickup_longitude - float for longitude coordinate of where the taxi ride started.
- pickup_latitude - float for latitude coordinate of where the taxi ride started.
- dropoff_longitude - float for longitude coordinate of where the taxi ride ended.
- dropoff_latitude - float for latitude coordinate of where the taxi ride ended.
- trip_distance -  float for distance of where the taxi ride traveled.
- passenger_count - integer indicating the number of passengers in the taxi ride(driver entered value).
- payment_type - str of what kind of payment the passenger done.
- tip amount - float how much  tip the passenger given.


This data is too large to fit into Pandas on a single computer. However, it can fit in memory if we break it up into many small pieces and load these pieces onto different computers across a cluster.

We connect a client to our Dask cluster, composed of one centralized dask-scheduler process and several dask-worker processes running on each of the machines in our cluster.
