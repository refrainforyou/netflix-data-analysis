# Netflix Data Analysis

This project explores the **Netflix Titles dataset** using Python and Pandas to perform data cleaning, feature engineering, and exploratory data analysis (EDA).

The goal of the project is to analyze Netflix content and identify patterns in **content distribution, genres, countries, release trends, and duration of movies and TV shows**.

---

# Project Structure

```
netflix-data-analysis
│
├── netflix_eda.ipynb
├── netflix_titles.csv
└── README.md
```

---

# Dataset

The dataset contains information about movies and TV shows available on Netflix.

Main columns:

- **show_id** – unique identifier
- **type** – Movie or TV Show
- **title** – title of the content
- **director** – director(s)
- **cast** – actors
- **country** – country of production
- **date_added** – date when the content was added to Netflix
- **release_year** – year of release
- **rating** – age rating
- **duration** – movie duration or number of seasons
- **listed_in** – genres
- **description** – short description

Dataset size: **~8800 titles**

---

# Technologies Used

- **Python**
- **Pandas**
- **Matplotlib**
- **Jupyter Notebook**

---

# Data Cleaning

Several preprocessing steps were performed to improve the quality of the dataset.

### Handling Missing Values

Missing values in categorical columns were handled by replacing them with **"Unknown"**:

- director
- cast
- country

### Date Processing

The `date_added` column was converted to **datetime format**.

Missing values were filled using the **mode** of the column.

### Duration Correction

Some rows had incorrect values where **duration values were placed in the rating column**.

These rows were corrected by moving the values back to the correct column.

### Removing Invalid Data

Rows with missing **rating values** were removed because rating is an important variable for analysis.

---

# Feature Engineering

To simplify analysis, the `duration` column was transformed into two separate features:

- **movie_minutes** – duration of movies in minutes
- **tv_seasons** – number of seasons for TV shows

Example:

duration → 90 min
movie_minutes → 90

duration → 3 Seasons
tv_seasons → 3

This allows analyzing movies and TV shows separately.

---

# Exploratory Data Analysis

Several exploratory analyses were conducted to better understand the dataset.

---

## Content Distribution

Analysis of the number of **Movies vs TV Shows** available on Netflix.

**Key finding:**

Movies dominate the catalog and represent the majority of Netflix content.

---

## Content Release Trends

Content was analyzed by **release year** to identify how Netflix content evolved over time.

**Key finding:**

Netflix content production increased significantly after **2016**, showing rapid platform growth.

---

## Country Analysis

Countries were analyzed to determine which ones produce the most Netflix content.

**Key findings:**

- The **United States** dominates the platform in terms of content production.
- Other countries contribute significantly smaller shares.

Analyses include:

- Top countries by number of titles
- Distribution of content by country

---

## Genre Analysis

The `listed_in` column contains multiple genres per title.  
To analyze genres correctly, the column was split and expanded using **split() and explode()**.

Analyses include:

- Most popular genres
- Genres for **Movies**
- Genres for **TV Shows**

---

## Director Analysis

Director data was analyzed to identify the most frequent directors.

Steps performed:

- Splitting multiple directors using `split()`
- Expanding rows using `explode()`
- Counting occurrences using `value_counts()`

---

## Duration Analysis

Movie duration and TV show seasons were analyzed separately.

Analyses include:

- Distribution of movie durations
- TV shows with the most seasons
- Longest movies in the dataset

---

# Key Insights

Main conclusions from the analysis:

- Netflix experienced significant growth after **2016**.
- **Movies dominate** the Netflix catalog compared to TV shows.
- The **United States is the main producer** of Netflix content.
- Some genres are significantly more common than others.
- Movie durations are relatively stable across the dataset.

---

# Example Visualizations

The notebook includes several visualizations such as:

- bar charts
- line charts
- pie charts
- distribution plots

These visualizations help better understand trends in Netflix content.

---

# Author

This project was created as part of a **Data Analyst portfolio** to demonstrate skills in:

- data cleaning
- feature engineering
- exploratory data analysis
- data visualization
- working with Pandas
