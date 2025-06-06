
# Disease Prediction Dashboard
# Overview
This Disease Prediction Dashboard is a Streamlit-based web application designed to analyze and predict COVID-19 and malaria cases in India using advanced time-series forecasting models, including LSTM and ARIMA. The dashboard provides interactive visualizations, risk assessments, and data-driven insights for public health analysis. It supports both historical data analysis and future case predictions, with customizable settings and an intuitive user interface.
Features

# Data Upload and Processing:
Preloaded COVID-19 data (January 2020 to May 2025) with simulation capabilities.
Upload and preprocess malaria datasets in CSV format(upload malaria_total1.csv).


# Forecasting:
LSTM Model: Forecasts COVID-19 cases and deaths with a configurable look-back period.
ARIMA Model: Predicts malaria cases for 2025 based on historical data (2020–2024).


# Visualizations:
Interactive plots using Plotly for COVID-19 trends.
Seaborn visualizations for malaria data, including correlation matrices, KDE plots, and bar charts.
Choropleth map for state-wise malaria risk in 2025.


# Risk Assessment:
Classifies states/UTs based on case counts into High, Medium, Moderate, and Low risk categories.


# User Profiles:
Save user information (name, email) and track analysis history.


# Customizable Settings:
Toggle between Light and Dark themes.
Adjust LSTM look-back period for forecasting.


# Combined Insights:
Compare annual trends and risks for COVID-19 and malaria.



# Requirements
To run the application, install the required Python packages listed in requirements.txt:
pip install -r requirements.txt

Key Dependencies:

pandas: Data manipulation and analysis.
streamlit: Web application framework.
numpy: Numerical computations.
seaborn, matplotlib: Static visualizations.
plotly: Interactive visualizations.
statsmodels: ARIMA and statistical modeling.
tensorflow: LSTM model implementation.
scikit-learn: Data preprocessing and metrics.

# Installation

Clone the Repository:
git clone <repository-url>
cd disease-prediction-dashboard


# Create a Virtual Environment (optional but recommended):
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


# Install Dependencies:
pip install -r requirements.txt


# Run the Application:
streamlit run main.py

The application will open in your default web browser at http://localhost:8501.


# Usage

# Home Page:

Process preloaded COVID-19 data or upload a malaria dataset (CSV format).

The malaria dataset should include columns for state/UT, blood slide examinations (BSE), malaria cases, Pf cases, and deaths for 2020–2024(upload malaria_total1.csv)


# COVID-19 Analysis:

View historical and forecasted cases/deaths using LSTM.
Select a forecast date range (post-May 27, 2025).
Explore metrics like MSE and R² for model performance.


# Malaria Analysis:

Visualize malaria trends, correlations, and top-affected states.
View ARIMA predictions for 2025 and risk classifications.
Explore a choropleth map for state-wise risk assessment.


# Combined Insights:

Compare annual trends and risks for COVID-19 and malaria (requires both datasets).


# Profile:

Update your name and email.
View the number of analyses run.


# Settings:

Switch between Light and Dark themes.
Adjust the LSTM look-back period (30–180 days).


# Reset App:

Use the sidebar "Reset App" button to clear all data and settings.



# Data Format

COVID-19 Data:

Preloaded data includes columns: Date_reported, Country, WHO_region, New_cases, Cumulative_cases, New_deaths, Cumulative_deaths.
Data is simulated from March 2020 to May 2025.


# Malaria Data (CSV):

Expected columns: STATE_UT, BSE_2020, Malaria_2020, Pf_2020, Deaths_2020, ..., up to 2024.
The preprocessing function handles missing or merged rows and converts data to numeric format.



# Notes

Performance: The application uses @st.cache_data to optimize performance for data processing, forecasting, and visualizations.
Error Handling: The app includes robust error handling for data parsing, model training, and visualization rendering.
Limitations:
LSTM forecasting requires sufficient historical data (at least as many days as the look-back period).
The choropleth map relies on an external GeoJSON file; ensure internet connectivity for rendering.
Forecasts are based on historical trends and may not account for real-world changes (e.g., new variants, policy changes).



#  Example Malaria Dataset
Sr,STATE_UT,BSE_2020,Malaria_2020,Pf_2020,Deaths_2020,BSE_2021,Malaria_2021,Pf_2021,Deaths_2021,...
1,GOA,10000,500,200,5,12000,600,250,6,...
2,MAHARASHTRA,50000,2000,1000,20,55000,2200,1100,22,...
...

# Future Improvements

Add support for additional diseases or datasets.
Implement detailed analysis history logging.
Enhance forecasting with exogenous variables (e.g., vaccination rates, weather data).
Add export functionality for visualizations and forecasts.
