Annual Taxi Report 2023 - Data Processing and Analysis

Overview

This project processes and analyzes taxi ride data from the Annual Taxi Report 2023 stored in a Parquet file. The workflow involves data cleaning, transformation, outlier handling, and visualization to gain insights into ride patterns, fare components, and trends.

Dataset

The dataset includes details on taxi rides such as passenger count, fare amount, trip distance, and additional charges. Key columns include:

tpep_pickup_datetime: Pickup timestamp

tpep_dropoff_datetime: Dropoff timestamp

fare_amount: Base fare cost

trip_distance: Distance traveled

RatecodeID: Rate code category

store_and_fwd_flag: Flag indicating if data was stored before forwarding

PULocationID/DOLocationID: Pickup/Drop-off location IDs

airport_fee: Charges related to airport pickups


Data Processing Steps

1. Data Loading

The dataset is loaded from a Parquet file using pandas.

Basic structure and first few records are displayed.

2. Data Cleaning

Identifies duplicate records.

Handles missing values by filling with mean values (e.g., passenger_count, RatecodeID, congestion_surcharge).

Merges airport_fee and Airport_fee into a single column (combined_airport_fee).

Converts categorical values (store_and_fwd_flag) to numerical representation (N=0, Y=1, None=2).

3. Outlier Removal

Interquartile Range (IQR) method is applied to remove outliers from numerical columns.

4. Feature Engineering

Extracts month, day of week, and hour from timestamps for time-based analysis.

Computes total fare components.


Data Visualization

1. Distribution Analysis

Fare Amount Histogram: Distribution of taxi fares.

Trip Distance Histogram: Distribution of travel distances.

2. Temporal Trends

Monthly Taxi Rides: Line plot showing the ride volume per month.

Taxi Rides by Day of the Week: Bar chart of ride frequency per weekday.

Hourly Ride Trends: Line plot showing peak hours for taxi rides.

3. Pickup and Drop-off Trends

Top 10 Pickup Locations: Bar chart for most frequent pickup points.

Top 10 Drop-off Locations: Bar chart for most common drop-off locations.

4. Fare Components Analysis

Total Contribution of Each Fare Component: Stacked bar chart visualizing fare breakdown.

Correlation Heatmap: Displays relationships between numerical variables such as fare amount, trip distance, and extra charges.



Tools & Libraries Used

Python (Data Processing & Visualization)

pandas (Data Manipulation)

numpy (Numerical Computations)

matplotlib & seaborn (Data Visualization)


How to Use

Ensure pandas, numpy, matplotlib, and seaborn are installed.

Update the file path for annual_report_2023.parquet if needed.

Run the script to process data and generate visualizations.


Future Improvements

Implement machine learning models for fare prediction.

Perform geospatial analysis for ride patterns.

Automate data pipeline for real-time analytics.
