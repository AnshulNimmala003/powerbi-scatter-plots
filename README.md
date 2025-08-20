# powerbi-scatter-plots
# 📊 Power BI Scatter Plot Project – IEM vs Firm Metrics

This project demonstrates how to build **jittered scatter plots in Power BI** to analyze the relationship between **IEM Labels (E, I, M)** and multiple **Firm CCII metrics** (Conservative, Aggressive, Acute, and Chronic).  

The goal was to overcome overlapping categorical points using jittering, apply consistent color coding, and deliver recruiter-ready visuals.

---

## 🚀 Project Overview
- Built in **Power BI Desktop**
- Dataset: *Climate Data RAND* (Excel source)
- Visuals: Scatter plots with jittered X-axis (E, I, M), Y-axis = firm metric values
- Exported PDF with all scatter plots for sharing without Power BI installed

---

## ✨ Features
- ✅ **Jittered scatter plots** to avoid overlapping points  
- ✅ **Consistent color coding** across all visuals (E = Green, I = Blue, M = Orange)  
- ✅ Comparison of multiple firm CCII metrics vs IEM labels  
- ✅ Exported **PDF report** for easy recruiter sharing  
- ✅ DAX-driven calculations for jitter and counts  

---

## 📂 Repository Structure
powerbi-scatter-plots/
│
├── README.md                  # Project documentation
├── scatter_plots.pbix          # Power BI report file (interactive)
├── scatter_plots1.pdf          # Exported visuals (ready to view)
│
└── data/                       # Example dataset 
└── Climate_data_RAND.xlsx

---

## 🛠️ DAX Highlights
Used DAX to create jittered X-axis values and keep IEM labels grouped:

```DAX
IEM Numeric =
SWITCH(
    TRUE(),
    'Solutions'[IEM] = "E", 1,
    'Solutions'[IEM] = "I", 2,
    'Solutions'[IEM] = "M", 3
)

IEM Jittered =
[IEM Numeric] + ( RAND() - 0.5 ) * 0.2
Color coding applied in Format → Data Colors:
	•	E = Green
	•	I = Blue
	•	M = Orange
