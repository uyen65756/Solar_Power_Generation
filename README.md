# Solar_Power_Generation

# ☀️ Solar Power Generation Prediction

This project uses environmental data to predict **solar power output** at a solar plant in Berkeley, CA. The dataset includes the following variables:

## 🌤 Input Features
- **🌞 distance_to_solar_noon** – Distance to solar noon (radians)  
- **🌡 temperature** – Daily average temperature (°C)  
- **🧭 wind_direction** – Daily average wind direction (°; 0–360)  
- **💨 wind_speed** – Daily average wind speed (m/s)  
- **☁️ sky_cover** – Cloud cover (0 = clear, 4 = fully covered)  
- **👀 visibility** – Visibility (km)  
- **💧 humidity** – Relative humidity (%)  
- **🌬 average_wind_speed** – 3-hour average wind speed (m/s)  
- **🌡️ average_pressure** – 3-hour average barometric pressure (inHg)  

## ⚡ Target Variable
- **🔋 power_generated** – Power generated in each 3-hour period (J)  

## 🎯 Project Goal
The goal is to predict power output under different environmental conditions to optimize solar plant performance.  
This project leverages machine learning techniques, including:
- **Feature Engineering**  
- **Residual Modeling**  
- **XGBoost Regression**  

These methods capture complex relationships between weather variables and energy production.  

## 💡 Inspiration
The project was inspired by methodologies implemented in [**Neural Designer**](https://www.neuraldesigner.com/learning/examples/solar-power-generation/), which applied a neural network to model solar power generation from environmental data.


## 📊 Highlights
- Baseline MAE: `2052.22`  
- XGBoost MAE: `571.93`  
- Visualizations include **polar plots** for solar noon & wind direction and **time series plots** for first & last 15 days.
