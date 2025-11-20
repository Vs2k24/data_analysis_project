# Netflix Movie Data Analysis 📊
A comprehensive data analysis project examining Netflix movie trends, ratings, and popularity metrics using Python, Pandas, Matplotlib, and Seaborn.

# 📋 Project Overview
This project analyzes a dataset of Netflix movies to uncover insights about movie genres, ratings, popularity trends, and release patterns. The analysis includes data preprocessing, categorization, and visualization to answer key questions about the Netflix movie catalog.

# 🎯 Key Findings
1. Most Frequent Genre: Drama is the most frequently occurring genre in the dataset
2. Highest Voted Category: Movies with "average" ratings received the most votes overall
3. Most Popular Movie: "Spider-Man: No Way Home" (2021) with genres: Action, Adventure, Science Fiction
4. Least Popular Movies: "The United States vs. Billie Holiday" and "Threads" with the lowest popularity scores
5. Peak Production Year: 2021 had the highest number of movies released

# 🛠️ Technologies Used
1. Python 3.x
2. Pandas - Data manipulation and analysis
3. NumPy - Numerical computations
4. Matplotlib - Data visualization
5. Seaborn - Statistical data visualization

# 📊 Dataset Structure
The dataset contains 9,827 movies with the following features:

1. Release_Date - Movie release date
2. Title - Movie title
3. Overview - Movie description
4. Popularity - Popularity score
5. Vote_Count - Number of votes received
6. Vote_Average - Average rating score
7. Original_Language - Original language of the movie
8. Genre - Movie genre(s)
9. Poster_Url - URL to movie poster

# 🔍 Analysis Process
1. Data Preprocessing
- Converted Release_Date from string to datetime, extracted year
- Removed unnecessary columns (Overview, Original_Language, Poster_Url)
-  Categorized Vote_Average into 4 categories:
   1. Not Popular
   2. Below Average
   3. Average
   4. Popular
- Split and exploded genre column for individual genre analysis
- Converted Genre column to categorical datatype for memory efficiency
- Checked and removed duplicate entries

2. Data Cleaning Highlights
  ```python

# Date conversion
df['Release_Date'] = pd.to_datetime(df['Release_Date']).dt.year

# Genre separation
df['Genre'] = df['Genre'].str.split(', ')
df = df.explode('Genre').reset_index(drop=True)

# Vote categorization
labels = ['not_popular', 'below_avg', 'average', 'popular']
df = categorize_col(df, 'Vote_Average', labels)
```
3. Key Analyses Performed
- Genre Distribution
   1. Identified Drama as the most frequent genre with 3,715 occurrences
   2. Created horizontal bar chart for genre frequency visualization.
- Vote Average Distribution
   1. Categorized votes into 4 tiers
   2. Average category had the highest count (6,613 movies)
- Popularity Analysis
   1. Maximum popularity: 5,083.954 (Spider-Man: No Way Home)
   2. Minimum popularity: 13.354 (multiple movies)
   3. Mean popularity: 41.97
- Temporal Analysis
   1. Analyzed movie release trends from 1902 to 2021
   2. Created histogram showing year-wise distribution
   3. Peak year: 2021 with 1,636 releases

# 📈 Visualizations
The project includes several visualizations:

1. Genre Distribution Bar Chart - Horizontal bar chart showing genre frequency
2. Vote Average Distribution - Category-wise vote distribution
3. Release Year Histogram - Distribution of movies across years

# 🚀 Getting Started
Prerequisites:

```python
pip install pandas numpy matplotlib seaborn
```
Running the Analysis:
- Clone the repository
- Ensure mymoviedb.csv is in the same directory
- Open and run the Jupyter notebook

```python
jupyter notebook "movie data analysis netflix.ipynb"
```

## 📝 Code Structure
```
├── Data Import & Initial Exploration
├── Data Preprocessing
│   ├── Date conversion
│   ├── Column removal
│   ├── Vote categorization
│   └── Genre separation
├── Data Analysis
│   ├── Genre frequency analysis
│   ├── Vote distribution analysis
│   ├── Popularity analysis
│   └── Temporal analysis
└── Data Visualization
```

## 🎓 Learning Outcomes

This project demonstrates:
- Data cleaning and preprocessing techniques
- Categorical data handling
- Custom function creation for data transformation
- Statistical analysis using Pandas
- Data visualization best practices
- Exploratory Data Analysis (EDA) methodology

## 📊 Sample Insights
```
Genre Distribution (Top 5):
1. Drama: 3,715 movies
2. Comedy: 2,400 movies
3. Thriller: 2,100 movies
4. Action: 2,000 movies
5. Romance: 1,800 movies

Popularity Statistics:
- Mean: 41.97
- Median: 21.84
- Max: 5,083.95 (Spider-Man: No Way Home)
- Min: 13.35
```

# 🔮 Future Enhancements
 - Add correlation analysis between popularity and vote count
 - Implement time-series analysis for genre trends
 - Create interactive visualizations using Plotly
 - Add predictive modeling for movie success
 - Include sentiment analysis on movie overviews

