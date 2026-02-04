# SpaceX Falcon 9 Landing Success Prediction

## Project Overview
This project analyzes historical **SpaceX Falcon 9 launch data** to **predict whether the first-stage booster will successfully land**. Successful landings are critical for rocket reusability and cost reduction.

The project follows the **complete data science lifecycle**:
**Data Collection → Data Wrangling → EDA → SQL Analysis → Interactive Visualization → Machine Learning**

This project was completed as part of the **IBM Data Science Professional Certificate Capstone**. 

## Problem Statement
SpaceX aims to reduce launch costs through reusable rocket technology.  
However, not all Falcon 9 missions result in successful first-stage landings.

### Key Questions
- What factors influence Falcon 9 first-stage landing success?
- Can landing success be predicted using machine learning?


## Dataset Description
The dataset consists of historical **SpaceX Falcon 9 launch records**, including:
- Flight number  
- Launch site  
- Payload mass  
- Orbit type  
- Booster version  
- Landing outcome (success/failure)  
- Launch date  


## Data Collection

### 1. SpaceX REST API
- Retrieved launch, rocket, booster, and landing data using SpaceX public APIs
- Automated API calls using Python (`requests`)
- Parsed JSON responses into structured pandas DataFrames

📘 Notebook: `spacex-data-collection-api.ipynb`


### 2. Web Scraping (Wikipedia)
- Scraped Falcon 9 historical launch records from Wikipedia
- Used:
  - `requests` for HTTP requests  
  - `BeautifulSoup` for HTML parsing
- Extracted table headers and rows
- Converted scraped data into a clean DataFrame

📘 Notebook: `webscraping.ipynb`


## Data Wrangling & Feature Engineering
- Identified data types for all features
- Counted unique values for each column
- Calculated missing value percentages
- Cleaned and standardized data
- Encoded landing outcomes:
  - `1` → Successful landing  
  - `0` → Failed landing  

📘 Notebook: `spacex-Data wrangling.ipynb`


## Exploratory Data Analysis (EDA)

### Data Visualization
Performed EDA using scatter plots, bar charts, and line plots to study:
- Payload mass vs Flight number
- Launch site vs Flight number
- Payload mass vs Launch site
- Orbit type vs Success rate
- Flight number vs Orbit type
- Yearly launch success trends

📘 Notebook: `edadataviz.ipynb`


### SQL Analysis
Used SQLite to query and analyze the dataset:
- Identified unique launch sites
- Calculated payload statistics by booster version
- Found the first successful ground landing date
- Counted successful and failed missions
- Analyzed booster versions with maximum payload
- Ranked landing outcomes over time

📘 Notebook: `eda-sql-coursera_sqllite.ipynb`


## Interactive Visual Analytics

### Folium Map
- Built an interactive world map of launch sites
- Marked launch sites using geographic coordinates
- Green markers → successful landings  
- Red markers → failed landings
- Calculated distances from launch sites to coastlines and nearby infrastructure
- Visualized proximities using polylines

📘 Notebook: `analytics_folium_map.ipynb`


### Plotly Dash Dashboard
Developed an interactive dashboard with:
- Dropdown menu to select launch site
- Pie charts showing launch success ratios
- Scatter plots of payload mass vs landing outcome
- Dynamic data filtering and visualization

📘 Script: `SpaceX_plotly.py`


## Machine Learning – Predictive Analysis

### Model Preparation
- Selected `Class` (landing success) as the target variable
- Normalized numerical features
- Split data into training, validation, and test sets

### Models Implemented
- Logistic Regression  
- Support Vector Machine (SVM)  
- Decision Tree  
- K-Nearest Neighbors (KNN)

### Model Optimization
- Used GridSearchCV for hyperparameter tuning
- Compared models using accuracy, confusion matrix, and F1-score

📘 Notebook: `SpaceX_Machine Learning Prediction.ipynb`


## Results
- Launch success rate increased significantly after **2013**
- **Launch site** and **orbit type** were the most influential features
- **SVM and KNN** performed best:
  - Validation accuracy ≈ **83%**
  - Test accuracy ≈ **77%**
- Confusion matrices showed strong true positive and true negative performance


## Key Insights
- Certain orbit types consistently showed higher success rates
- Payload mass alone does not determine landing success
- SQL queries enabled deeper insights beyond traditional EDA
- Visual analytics helped identify the most impactful features


## Conclusion
This project demonstrates how **data science and machine learning** can be applied to real-world aerospace problems. By analyzing historical SpaceX launch data, the project identifies key success factors and builds reliable predictive models to support reusable rocket technology.


## Technologies Used
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- SQL (SQLite)  
- Folium  
- Plotly Dash  
- Scikit-learn  
- REST APIs  
- Web Scraping (BeautifulSoup)
