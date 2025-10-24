# 🚆 Preventing APU Failures in Metro Trains: A Predictive & Visual Analytics Approach

This repository contains the implementation and results of the thesis **"Preventing APU Failures in Metro Trains: A Predictive and Visual Analytics Approach"**, carried out as part of the **Master of Science in Data Science** program at **Vellore Institute of Technology (VIT), Chennai**.

---

## 🎯 Project Overview

Metro trains rely on **Auxiliary Power Units (APUs)** to power essential onboard systems such as braking, air conditioning, and lighting. Unexpected APU failures can lead to costly downtime and service interruptions.

This project develops a **Predictive Maintenance Framework** using:

- **Power BI** for Exploratory and Visual Analytics
- **Machine Learning and Deep Learning Models** for failure classification
- **Time Series Modeling (VAR)** for forecasting critical sensor signals

The goal is to detect faults early, optimize maintenance schedules, and improve system reliability.

---

## 📊 Dataset Information

- **Dataset Used:** MetroPT / MetroPT-3 (UCI Repository)
- **Records:** 1,516,948 multivariate time-series sensor readings
- **Sensors:** Pressure, Temperature, Motor Current, Valve Signals, etc.

### Key Selected Features (After Feature Importance & Power BI Dashboard Analysis)

| Feature | Description |
|--------|-------------|
| TP3 | Pneumatic panel pressure |
| Motor_current | Compressor motor load |
| Oil_temperature | Thermal state of compressor |
| DV_pressure | Dryer valve pressure |
| Reservoirs | Storage tank pressure |
| Pressure_switch | Electrical pressure signal |
| Oil_level | Lubrication level |

These features were identified as the **primary contributors to APU failure events**.

---

## 🧠 Predictive Models Implemented

### Machine Learning Models
| Model | Performance Summary |
|------|---------------------|
| Logistic Regression | Baseline comparison |
| Random Forest | High stability and recall |
| **XGBoost** | **Best performer (~96% accuracy)** |
| SVM | Moderate performance |

### Deep Learning Models
| Model | Architecture | Observations |
|------|-------------|--------------|
| ANN | Dense layers | High accuracy, balanced performance |
| DNN | Deeper dense layers | Tended to overfit |
| CNN (1D) | Convolution filters on sequence data | Limited improvement for this problem |
| **Hybrid ANN-CNN** | Feature extraction + dense classification | **Best DL performance (~89%)** |

---

## ⏱ Time Series Forecasting (VAR Model)

The **Vector Autoregression (VAR)** model was used to capture relationships between sensor signals across time.

### Stationarity Test
All selected variables passed the **ADF Test**, confirming stationarity and suitability for time-series modeling.

### Forecast Performance

| Parameter | MAE | RMSE | MAPE (%) | Observations |
|----------|------|------|----------|--------------|
| TP3 | 0.0091 | 0.0129 | 0.10 | **Highly accurate forecast** |
| Oil Temperature | 0.0806 | 0.0862 | 0.14 | Very closely predicted |
| Motor Current | 0.2042 | 0.2355 | 465.77 | Sudden spikes reduce accuracy |
| DV Pressure | 0.0014 | 0.0020 | 6.79 | Fluctuations need smoothing |

TP3 and Oil Temperature were forecasted **very accurately**, while parameters with abrupt fluctuations require refined modeling.

---

## ✅ Key Outcomes

- **XGBoost** was the best-performing model for failure classification.
- **Hybrid ANN-CNN** achieved the strongest performance among deep learning models.
- **VAR Time-Series Model** successfully forecasted critical APU operating parameters.
- Power BI visual insights helped reveal **which sensor behaviors lead to failures**.

---

## 🏁 Conclusion

The project demonstrates that **data-driven predictive maintenance** can significantly reduce unexpected failures in metro APUs.  
By integrating **visual analytics + predictive models + time-series forecasting**, rail operators can:

- Detect failures earlier
- Reduce downtime and repair cost
- Enhance safety and reliability of metro systems

---

## 👤 Author

**Gowthami A**  
M.Sc. Data Science  
Vellore Institute of Technology (VIT), Chennai

