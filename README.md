# Energy Consumption Prediction for Ro-Ro Vessels from Sensor Data

## Project Overview
This project focuses on developing a predictive model to estimate the energy consumption of the MS Smyril, a Danish roll-on/roll-off passenger ship, using sensor data collected over two months in 2010. The dataset includes over 1.6 million records from various sensors such as Doppler speed logs, GPS, gyrocompass, and rudder angles. The goal is to optimize fuel usage and improve efficiency in maritime transportation by providing accurate energy consumption predictions.

## Key Features

### Data Processing:
- Energy consumption (EC) was calculated using fuel density and volume flow rate:
EC = fuelDensity * fuelVolumeFlowRate
- Data was aggregated into one-minute intervals to handle non-uniform timestamps and ensure sufficient data points for accurate predictions.
- Outliers and discontinuities (e.g., gaps between journeys) were removed to clean the dataset.

### Feature Engineering:
- Combined wind speed and direction into a single feature (`wind_effect`) to account for their impact on ship movement.
- Selected key features (longitudinal water speed, port pitch, starboard pitch) based on correlation analysis.

### Modeling:
- **Random Forest**: Achieved an R² score of 0.988, capturing nonlinear relationships and demonstrating robustness to noise.
- **SVR (Support Vector Regression)**: Achieved an R² score of 0.986 with an RBF kernel, performing comparably to Random Forest.
- **Ridge Regression**: Achieved a lower R² score of 0.702, highlighting the limitations of linear models for this task.

## Results
- Random Forest and SVR outperformed Ridge Regression, demonstrating the importance of nonlinear models for this problem.
- Feature importance analysis revealed that starboard pitch and longitudinal water speed were the most influential predictors of energy consumption.

## Conclusion
This project successfully leveraged sensor data to predict ship energy consumption, with Random Forest and SVR emerging as the top-performing models. The results underscore the potential of machine learning to optimize fuel efficiency in maritime operations.

