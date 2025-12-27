# 🍽️ Geospatial Data Analytics — Zomato Dataset  

## 🧠 Overview  
This project performs **Geospatial and Text Analytics** on Zomato restaurant data to explore cuisine trends, customer preferences, and restaurant distribution across Indian cities.  

It combines **Natural Language Processing (NLP)**, **Exploratory Data Analysis (EDA)**, and **Geospatial Mapping** to uncover hidden insights from restaurant data such as most popular cuisines, customer sentiment, and high-density restaurant areas.

---

## 🎯 Project Objectives  
- Clean and preprocess raw Zomato data for analysis  
- Perform text analysis on customer reviews to identify common opinions  
- Analyze restaurant ratings and online order availability  
- Visualize restaurant density geographically using interactive maps  
- Explore relationships between location, cuisine type, and popularity  

---

## 🧰 Tools & Libraries  
| Category | Libraries |
|-----------|------------|
| Data Analysis | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `plotly`, `folium` |
| Geospatial Mapping | `geopy`, `folium.plugins.HeatMap` |
| Text Analysis | `nltk` (tokenizer, stopwords) |
| Cleaning | `re`, `string`, `warnings` |

---

## 🧩 Project Workflow  

### 1️⃣ Data Loading and Cleaning  
- Imported the Zomato dataset using `pandas`  
- Removed duplicates and missing values  
- Standardized location and cuisine names  
- Cleaned review text (lowercasing, removing punctuation, filtering stopwords)

---

### 2️⃣ Text Analysis (Unigrams & Bigrams)  
Text data from reviews was tokenized and analyzed to identify the most frequent single words (unigrams) and word pairs (bigrams).

#### 🔹 **Bigram Frequency (Top 20 Most Common Word Pairs)**
The plot below shows the most common phrases used in customer reviews.  
For example, customers frequently mentioned “The food”, “I ordered”, and “really good”.

![Bigram Frequency](./Screenshot%202025-12-27%20191759.png)

📊 **Interpretation:**  
- The most frequent word pair is “The food”, showing that food quality dominates customer discussions.  
- Other popular phrases like “really good” and “must try” indicate positive feedback trends.  

---

#### 🔹 **Word Frequency (Unigrams)**
This chart displays the most commonly used words across all reviews.  
Words like “place”, “good”, and “food” appear most frequently.

![Word Frequency](./Screenshot%202025-12-27%20191805.png)

📊 **Interpretation:**  
- “Place”, “good”, and “food” are the most common — meaning customers focus primarily on the restaurant atmosphere and food quality.  
- Words like “chicken”, “taste”, and “service” suggest recurring interest in food quality and service standards.

---

### 3️⃣ Rating vs Online Order Analysis  
Restaurants were analyzed based on their ratings and whether they provide online ordering options.

#### 🔹 **Percentage Distribution of Online Orders**
The following chart shows the percentage of restaurants offering online orders across different rating levels.

![Online Order % Distribution](./Screenshot%202025-12-27%20191831.png)

📊 **Interpretation:**  
- Restaurants with ratings between **3.5 and 4.5** are more likely to offer online delivery.  
- Low-rated restaurants (below 3.0) have fewer online order facilities.

---

#### 🔹 **Count of Restaurants (Stacked by Online Order Availability)**
This stacked bar chart shows the number of restaurants at each rating level, divided by online order availability.

![Online Order Count Distribution](./Screenshot%202025-12-27%20191839.png)

📊 **Interpretation:**  
- Most restaurants cluster around **3.5 to 4.0 ratings**, which are considered average to good.  
- Online ordering is dominant in mid-to-high-rated restaurants, while very high-rated (above 4.5) restaurants rely more on dine-in services.

---

### 4️⃣ Geospatial Visualization — Restaurant Density Map  
Using **Folium** and **Geopy**, we mapped restaurant coordinates to visualize geographical density.

```python
from folium.plugins import HeatMap
m = folium.Map(location=[12.9716, 77.5946], zoom_start=12)
HeatMap(df[['latitude', 'longitude']]).add_to(m)
m
