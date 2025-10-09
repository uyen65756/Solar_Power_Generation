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
- **Weighted LSTM Sequence Correction** – gently smooths XGBoost residuals over time for improved trend prediction.

These methods capture complex relationships between weather variables and energy production, while preserving sudden drops and short-term variability.

## 💡 Inspiration
The project was inspired by methodologies implemented in [**Neural Designer**](https://www.neuraldesigner.com/learning/examples/solar-power-generation/), which applied a neural network to model solar power generation from environmental data.

## 📊 Highlights
- Baseline MAE: `2052.22`  
- XGBoost MAE: `571.93`  
- Weighted LSTM sequence correction MAE: `625.96` (alpha = 0.2)  
- Visualizations include:
  - **Time series plots** for first & last 15 days comparing Baseline, XGBoost, and XGB + Weighted LSTM predictions  
  - **Polar plots** for Solar Noon & Wind Direction, showing absolute errors for Baseline, XGBoost, and XGB + Weighted LSTM  

**Note:** Weighted LSTM residual correction smooths minor fluctuations without overcorrecting sudden drops, providing a stable, realistic forecast while retaining XGBoost’s accuracy for abrupt events.

---

## 📝 Conclusion / Next Steps
- **Conclusion:** XGBoost captures the majority of solar power variability, while the weighted LSTM sequence improves trend smoothness and residual modeling without overfitting. Visualizations confirm that the combined approach preserves sudden drops and daily patterns.  
- **Next Steps:**  
  1. Incorporate environmental features into the LSTM input for more anticipatory corrections.  
  2. Explore hyperparameter tuning for sequence length, hidden size, and alpha weighting.  
  3. Evaluate performance on longer forecast horizons (multi-step ahead predictions).  
  4. Investigate additional residual modeling techniques, such as convolutional LSTMs or attention mechanisms, for capturing short-term spikes and drops more accurately.
