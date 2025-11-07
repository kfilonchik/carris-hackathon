# 🚍 Carris Hackathon — Bus Exit Estimation Using Mobility Data

This repository contains the full analytical pipeline developed for the **Carris Hackathon**, where the main challenge was the **estimation of bus exits (alightings)** using operational Carris data.  
The project combines **data preparation**, **graph-based mobility analysis**, and **predictive modelling** using a gravity model.

Github: https://github.com/kfilonchik/carris-hackathon/blob/main/README.md

---

## 📁 Project Structure

The analysis is divided into three Jupyter notebooks:

---

### 1️⃣ Data Preparation  
**Notebook:** `01_data_preparation.ipynb`

This notebook performs all preprocessing steps required for the analysis:

- Cleaning and harmonising raw datasets  
- Parsing and aligning timestamps  
- Enriching vehicle events with validation (check-in) data  
- Spatial matching of events to stop locations  
- Integrating GTFS, route, and calendar information  

---

### 2️⃣ Mobility Analysis with City2Graph  
**Notebook:** `02_frequency_duration_city2graph.ipynb`

This notebook uses **City2Graph** to transform Carris bus operations into a graph structure and analyse:

- Service frequency per edge  
- Average durations and timing patterns  
- Spatial filtering to keep only Lisbon-related services  
- Network topology and connectivity  
- Identification of inconsistencies or data gaps  

**Output:** A graph-based representation of the Carris network with frequency and duration metrics.

---

### 3️⃣ Exit Prediction Using a Gravity Model  
**Notebook:** `03_gravity_model_prediction.ipynb`

This notebook implements a **singly constrained Gravity Model** (via `scikit-mobility`) to estimate **where passengers exit buses**, based on:

- Observed inflows (validation counts)  
- Network structure  
- Distance-based deterrence functions  
- Fitted parameters (destination exponent, lambda)  

Includes:

- Model fitting and parameter extraction  
- Performance indicators (AIC, convergence)  
- Generation of synthetic flows (predicted alightings)  
- Visualisation and interpretation of results  

**Output:** Predicted exit flows for each stop in the Carris bus network.

---

## 🛠️ Technologies Used

- Python  
- Pandas / NumPy  
- GeoPandas  
- City2Graph  
- Scikit-Mobility  
- Statsmodels  
- Folium / Matplotlib  
- OSMnx  

---

## 🎯 Goal

To build an **end-to-end mobility analysis pipeline** that predicts **bus exit behaviour** using available operational data.  
These insights can support:

- Better service planning  
- Route adjustments  
- Demand estimation  
- Understanding origin–destination patterns  
- Improving overall public transport efficiency  
