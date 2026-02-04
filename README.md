SpaceX Falcon 9 Landing Success Prediction

Project Overview
This project analyzes historical SpaceX Falcon 9 launch data to predict whether the first-stage booster will successfully land. Successful landings are critical for rocket reusability and cost reduction.

The project applies the complete data science lifecycle:
data collection → data wrangling → exploratory data analysis → SQL analysis → interactive visualization → machine learning modeling.

📄 This project is part of the IBM Data Science Professional Certificate Capstone  ￼


Problem Statement
SpaceX aims to reduce launch costs by reusing the Falcon 9 first-stage boosters.
However, not every mission results in a successful landing.

Key Questions:
	•	What factors influence Falcon 9 first-stage landing success?
	•	Can landing success be predicted using machine learning models?


🗂️ Dataset Description
The dataset contains historical SpaceX Falcon 9 launch records, including:
	•	Flight number
	•	Launch site
	•	Payload mass
	•	Orbit type
	•	Booster version
	•	Landing outcome (success/failure)
	•	Launch date


🔍 Data Collection
Data was collected using two approaches:

1️⃣ SpaceX REST API
	•	Used SpaceX public API to retrieve:
	•	Launch details
	•	Rocket and booster information
	•	Landing outcomes
	•	Automated API requests using Python (requests)
	•	Converted JSON responses into structured pandas DataFrames
📌 Notebook: spacex-data-collection-api.ipynb  ￼


2️⃣ Web Scraping (Wikipedia)
	•	Scraped Falcon 9 historical launch records from Wikipedia
	•	Used:
	•	requests to fetch HTML pages
	•	BeautifulSoup to parse tables
	•	Extracted column names and rows
	•	Converted scraped data into a clean DataFrame
📌 Notebook: webscraping.ipynb  ￼


🧹 Data Wrangling & Feature Engineering
Performed essential preprocessing steps:
	•	Identified data types of all columns
	•	Counted unique values per feature
	•	Calculated missing value percentages
	•	Cleaned and standardized data
	•	Encoded the landing outcome:
	•	1 → Success
	•	0 → Failure
This label was used for supervised machine learning.
📌 Notebook: spacex-Data wrangling.ipynb  ￼


📊 Exploratory Data Analysis (EDA)
📈 Data Visualization
Used matplotlib and seaborn to explore relationships between variables:
	•	Payload mass vs Flight number
	•	Launch site vs Flight number
	•	Payload mass vs Launch site
	•	Orbit type vs Success rate
	•	Flight number vs Orbit type
	•	Yearly launch success trends
Key insights were visually identified through scatter plots, bar charts, and line graphs.
📌 Notebook: edadataviz.ipynb  ￼


🗄️ SQL Analysis
Used SQL (SQLite) to query the dataset for deeper insights:
	•	Unique launch sites
	•	Payload statistics by booster version
	•	First successful ground landing date
	•	Success vs failure counts
	•	Booster versions with maximum payload
	•	Failed drone ship landings by year and site
	•	Ranking landing outcomes over time
📌 Notebook: eda-sql-coursera_sqllite.ipynb  ￼


🗺️ Interactive Visual Analytics
🌍 Folium Map
Built an interactive geographic map:
	•	Plotted all SpaceX launch sites
	•	Green markers → successful landings
	•	Red markers → failed landings
	•	Calculated distances to coastlines and nearby infrastructure
	•	Drew polylines to analyze site proximities
📌 Notebook: analytics_folium_map.ipynb  ￼


📊 Plotly Dash Dashboard
Developed an interactive dashboard with:
	•	Dropdown to select launch site
	•	Pie charts showing success ratios
	•	Scatter plots of payload vs landing outcome
	•	Dynamic data filtering and exploration
📌 Script: SpaceX_plotly.py  ￼


🤖 Machine Learning – Predictive Analysis
Model Preparation
	•	Selected Class (landing success) as target variable
	•	Normalized numerical features
	•	Split data into:
	•	Training set
	•	Validation set
	•	Test set

Models Implemented
	•	Logistic Regression
	•	Support Vector Machine (SVM)
	•	Decision Tree
	•	K-Nearest Neighbors (KNN)

Model Optimization
	•	Used GridSearchCV for hyperparameter tuning
	•	Compared models using:
	•	Validation accuracy
	•	Test accuracy
	•	Confusion matrix
	•	F1-score

📌 Notebook: SpaceX_Machine Learning Prediction.ipynb  ￼


Results
	•	Launch success rate increased significantly after 2013
	•	Launch site and orbit type had the strongest impact on landing success
	•	SVM and KNN performed best:
	•	Validation accuracy ≈ 83%
	•	Test accuracy ≈ 77%
	•	Confusion matrices showed high true positives and true negatives


Key Insights
	•	Certain orbit types (LEO, GEO, HEO, SSO) consistently showed higher success rates
	•	Heavier payloads did not always reduce success probability
	•	Visual analytics and SQL provided deeper insights than basic EDA alone
	•	Feature selection and visualization were crucial for model performance


Conclusion

This project demonstrates how data science and machine learning can be used to:
	•	Analyze real-world aerospace data
	•	Identify key operational factors
	•	Build predictive models for mission success
	•	Support cost reduction strategies through data-driven decisions


🛠️ Technologies Used
	•	Python
	•	Pandas, NumPy
	•	Matplotlib, Seaborn
	•	SQL (SQLite)
	•	Folium
	•	Plotly Dash
	•	Scikit-learn
	•	REST APIs
	•	Web Scraping (BeautifulSoup)
