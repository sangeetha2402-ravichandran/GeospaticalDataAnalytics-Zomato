# 🍽️ Geospatial Data Analytics — Zomato Dataset

## 🧠 Overview
This project performs **Geospatial and Text Analytics** on the **Zomato restaurant dataset** to uncover insights into restaurant distribution, customer preferences, cuisine trends, and location-based patterns.

It integrates **Exploratory Data Analysis (EDA)**, **Natural Language Processing (NLP)**, and **Geospatial Visualization** to better understand how geography and cuisine types influence restaurant performance.

---

## 🎯 Objectives
- Clean and preprocess Zomato restaurant data for analysis  
- Explore restaurant distribution by city, rating, and cuisine  
- Perform **text processing** on restaurant reviews (tokenization, stopword removal, normalization)  
- Use **geocoding** to map restaurant locations  
- Visualize city and cuisine density using **interactive heatmaps**  
- Identify location-based trends and cuisine popularity  

---

## 🧰 Tools & Libraries Used
| Category | Libraries |
|-----------|------------|
| Data Handling | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `plotly`, `folium` |
| Geospatial Analysis | `geopy`, `folium.plugins.HeatMap` |
| Text Processing | `nltk` (tokenizer, stopwords) |
| Data Cleaning | `re`, `string`, `warnings` |

---

## 🧩 Workflow

### 1️⃣ Data Loading & Cleaning
- Load the raw Zomato dataset (`zomato.csv`)  
- Handle missing or inconsistent entries  
- Normalize column names and remove irrelevant features  

### 2️⃣ Text Processing
- Convert text to lowercase  
- Tokenize reviews and remove punctuation  
- Remove stopwords using `nltk.corpus.stopwords`  
- Analyze frequent words or phrases in reviews  

### 3️⃣ Geocoding Restaurant Locations
- Use `geopy.Nominatim` to fetch latitude and longitude for each location  
- Handle missing or unrecognized locations with error handling  
- Save latitude & longitude columns for visualization  

### 4️⃣ Geospatial Visualization
- Use **Folium** to create interactive maps  
- Plot all restaurants as markers  
- Build **HeatMaps** to visualize restaurant density by location or cuisine  
- Example:
  ```python
  from folium.plugins import HeatMap
  m = folium.Map(location=[12.9716, 77.5946], zoom_start=12)
  HeatMap(df[['latitude', 'longitude']]).add_to(m)
  m
