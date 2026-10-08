# Netflix Content Analysis: Python & Tableau

A data analysis project using the [Netflix Movies and TV Shows dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows) from Kaggle (8,807 titles added to Netflix between 2008 and 2021).

- **`Netflix Content Analysis.ipynb`**: the analysis. It loads, explores and cleans the data, answers 15 business questions with charts, and ends with key findings.
- **`Netflix Content Data Analysis Dashboard.twbx`**: an interactive Tableau dashboard built from the cleaned data.

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook, Tableau

![Dashboard](Netflix%20Content%20Analysis%20Dashboard.png)

## Business questions

1. What share of the catalog is Movies vs TV Shows?
2. How has the content library grown over the years?
3. Which countries produce the most content?
4. Which genres are most common?
5. What are the most common content ratings?
6. Which release years have the most titles?
7. Which directors appear most often?
8. Which actors appear most often?
9. How long are most movies?
10. How many seasons do most TV shows have?
11. Which months have the most titles added?
12. How have Movies and TV Shows additions changed over time?
13. Which countries produce the most Movies and TV Shows?
14. Which genres are most common for Movies and for TV Shows?
15. Which 15 countries have the most titles?

## Data cleaning

- Filled missing `director`, `cast`, `country`, `rating` and `duration` values with `Unknown`.
- Converted `date_added` to a date and created `year_added`, `month_added`, `month_name` and `day_added`.
- Created `decade` from `release_year`.
- Split `duration` into `movie_duration` (minutes) and `tv_seasons` (number of seasons).
- Created `main_country` (the first country listed for each title).
- Saved the result to `netflix_cleaned.csv` (8,807 rows, 20 columns), which the Tableau dashboard uses.

## Key insights

- **Movies make up about 70%** of the catalog (6,131 movies vs 2,676 TV shows).
- Content additions grew fast from **73 titles in 2015 to 1,999 in 2019**, the peak year, then slowed in 2020 and 2021.
- The **United States** produces the most content, followed by **India** and the **United Kingdom**. Canada, France, Japan, South Korea and Spain also contribute a lot.
- **International Movies, Dramas and Comedies** are the most common genres.
- **TV-MA** is the most common rating (3,207 titles, about 36%), followed by TV-14. The catalog is aimed mostly at adults and teens.
- **94%** of titles were released in 2000 or later.
- The median movie runs **98 minutes**, and about 64% of movies are 80–120 minutes long.
- **67%** of TV shows have only one season, and 83% have one or two.
- **July** and **December** are the months with the most titles added.
- Indian actors such as **Anupam Kher** and **Shah Rukh Khan** appear most often, which shows how large the Indian catalog is.

## Project structure

```
├── Netflix Content Analysis.ipynb                data analysis notebook
├── Netflix Content Data Analysis Dashboard.twbx  Tableau dashboard (packaged workbook)
├── Netflix Content Analysis Dashboard.png        dashboard screenshot
├── netflix_data.csv                              raw dataset from Kaggle
└── netflix_cleaned.csv                           clean data saved by the notebook
```

## How to run

```bash
python -m venv .venv
.venv\Scripts\activate          # macOS/Linux: source .venv/bin/activate
pip install pandas numpy matplotlib seaborn notebook

# Open the notebook and run all cells (this also saves netflix_cleaned.csv)
jupyter notebook "Netflix Content Analysis.ipynb"
```

To view the dashboard, open `Netflix Content Data Analysis Dashboard.twbx` in [Tableau Desktop](https://www.tableau.com/products/desktop) or the free [Tableau Public](https://public.tableau.com/app/discover) app.

## Dashboard

The Tableau dashboard shows:

- KPI cards: total titles, movies, TV shows and number of countries
- Netflix content added by year
- Movies vs TV Shows
- Ratings breakdown
- Top 10 countries by Netflix titles
- Top 10 genres by number of titles
