# Seoul Bike Sharing Demand Prediction

![alt text](</images/Seoul Bike Sharing Demand Prediction project cover page, 4x3, height 1_2 of the width.png>)

## Problem Statement
The Seoul Bike Sharing program has been a significant success in promoting eco-friendly transportation and reducing traffic congestion. However, one of the challenges faced by the program is ensuring an adequate supply of bikes at each station throughout the day. The goal of this project is to predict the number of bikes required at each hour to minimize waiting times and improve user satisfaction.

## Dataset
The dataset used for this project is the Seoul Bike Sharing Demand dataset, which includes the following features:

1. Date - The specific date of observation.
2. Rented Bike Count - The number of bikes rented at each hour.
3. Hour - The hour of the day (0 to 23), when the observation was recorded.
4. Temperature (°C) - The temperature at the time of observation (celsius).
5. Humidity (%) - The relative humidity percentage at the time of observation.
6. Wind Speed (m/s) - The wind speed in meters per second.
7. Visibility (10m) - Visibility in units of 10m
8. Dew Point Temperature (°C) - The temperature at which air becomes saturated and produces dew (celsius).
9. Solar Radiation (MJ/m²) - The amount of solar radiation in MegaJoules per square meter.
10. Rainfall (mm) - The amount of rainfall in millimeters at time of observation.
11. Snowfall (cm) - The amount of snowfall in centimeters at time of observation.
12. Seasons (Winter, Spring, Summer, Autumn) - The season in which the observation was recorded.
13. Holiday (Holiday/No holiday) - Whether the observation was recorded on a holiday.
14. Functional Day (NoFunc for Non-Functional Hours, Fun for Functional hours)

## Objective
The primary objective of this project is to develop a machine learning model that can accurately predict the number of bikes required at each hour based on historical data and weather conditions. This will help in optimizing the distribution of bikes across different stations and ensuring a smooth user experience.

## Approach
### Data Preprocessing:

1. Clean the dataset by handling missing values and outliers.

2. Convert categorical variables into numerical representations.

3. Normalize or standardize the numerical features.

### Exploratory Data Analysis (EDA):

1. Analyze the distribution of bike rentals across different hours, days, and seasons.

2. Identify correlations between bike rentals and weather conditions.

3. Visualize the data to gain insights into patterns and trends.

### Model Selection and Parameter Tuning:
- Experiment with various machine learning algorithms such as Linear Regression, Decision Trees, Random Forest, and XGBoost.
- Evaluate the performance of each model using metrics like Mean Squared Error (MSE), and R-squared, while fine tuning hyperparameters to come up with the best outcome.

### Model Training and Evaluation:
- Split the dataset into training and testing sets.
- Train the best performing model on the training data.

### Deployment:

Deploy the trained model as a web service or API.

Integrate the model with the bike sharing system to provide real-time predictions.

## Project Structure
```
/data
    seoul+bike+sharing+demand.zip
    SeoulBikeData.csv
/logs
    app.log
    training.log
/models
    bike_sharing_model.pkl
/notebooks
    notebook.ipynb
    testing_notebook.ipynb
/scripts
    training_script.py
app.py
Dockerfile
Pipfile
Pipfile.lock
readme.md
```

## Installation
To set up the project locally, follow these steps:
1. Clone the repository: `git clone git@github.com:okellodaniel/bike_share_regression.git`
2. Navigate to the project directory: `cd bike_share_regression`
3. Install the required dependencies: `pip install -r requirements.txt`

## Running the Project
### Locally
1. Ensure all dependencies are installed.
2. Run the application: `python app.py`
3. Access the web service at `http://localhost:5000` to get predictions.
4. Access the web dashboard at `http://localhost:5000/dashboard` to visualize the data.

### Using Docker
1. Build the Docker image: `docker build -t bike-sharing-prediction .`
2. Run the Docker container: `docker run -p 5000:5000 bike-sharing-prediction`
3. Access the web service at `http://localhost:5000`.

### Testing the Deployed Version
1. Access the deployed version at [`https://bike-share-regression.fly.dev/`](`https://bike-share-regression.fly.dev/`) to get predictions.

## Testing with Curl
To test the API using `curl`, use the following command with the sample payload:
```bash
curl -X POST http://localhost:5000/ -H "Content-Type: application/json" -d "{
  'temperature_c': 12.2,
  'humidity': 14,
  'wind_speed_ms': 1.6,
  'visibility_10m': 1896,
  'dew_point_temperature_c': -14.5,
  'solar_radiation_mjm2': 2.75,
  'rainfallmm': 0.0,
  'snowfall_cm': 0.0,
  'seasons': 'spring',
  'holiday': 'no_holiday',
  'functioning_day': 'yes',
  'month': 3,
  'day': 3,
  'dayofweek': 5,
  'hour_sin': -0.25881904510252035,
  'hour_cos': -0.9659258262890684
}"
```

## Results
The model achieved an R-squared value of 0.94, indicating a strong correlation between the predicted and actual bike demand.

## Contributing
Contributions are currently not welcome! But please fork the repository and submit a pull request for any improvements or bug fixes.
