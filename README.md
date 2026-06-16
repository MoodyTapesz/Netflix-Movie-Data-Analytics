# Netflix-Movie-Data-Analytics
Analyzing Netflix movie data using Python and Pandas. 

# Netflix Movie Data Analytics 🎬📊

An end-to-end data exploration and analytics project on a dataset containing nearly 10,000 movie records. This project focuses on cleaning, handling multi-valued attributes, engineering data columns, and deriving graphical insights using Python's scientific stack.

---

📌 Project Overview
The objective of this project is to clean a messy movie database and discover underlying trends regarding film genres, user ratings, release years, and market popularity. The original raw dataset contains multiple genres packed into single rows and continuous numerical variables that required bucketing for meaningful insights.

🛠️ Tech Stack & Libraries
* Language: Python 3.12
* **Libraries:** 
* **Pandas:** Data manipulation, column casting, exploding multi-valued rows, and statistical profiling.
  * **NumPy:** Numerical calculations and handling structure.
  * **Matplotlib & Seaborn:** Custom categorical counts, histogram mapping, and aesthetic chart formatting.

---

🔍 Key Data Engineering Steps
1. **Temporal Features:** Converted raw strings in `Release_Date` to datetime objects and extracted only the relevant release year.
2. **Feature Selection:** Dropped text-heavy, high-cardinality, or non-analytical columns including `Overview`, `Original_Language`, and `Poster_Url`.
3. **Statistical Binning (Custom Quantiles):** Built a custom function `categorize_col()` to automatically calculate statistical quartiles (min, 25%, 50%, 75%, max) and cut the `Vote_Average` continuous score into four distinct buckets: `flop`, `below_avg`, `average`, and `popular`.
4. **Data Explosion (Handling Multi-Genres):** The `Genre` column originally contained comma-separated lists (e.g., "Action, Adventure, Sci-Fi"). The data was split into a list format and "exploded" using pandas so that each single genre occupies its own row for independent tracking.

---

📊 Analytics & Insights Discovered

#1. Most Frequent Film Genre
* **Drama** is the most frequent genre of movie released on the platform, appearing over 3,700 times within the expanded rows.

#2. Rating Distributions
* The dataset divides smoothly into statistically uniform parts following quantile bucketing, where `average` configurations represent the slight peak frequency.
* When breaking down popularity metrics, **Drama** consistently leads user engagement and volume.

#3. Maximum & Minimum Popularity Outliers
* 🚀 **Highest Popularity Movie:** *Spider-Man: No Way Home* (Popularity index: **5083.95**)
  * **Genres:** Action, Adventure, Science Fiction.
* 📉 **Lowest Popularity Movies:** *The United States vs. Billie Holiday* & *Threads* (Popularity index: **13.35**)
  * **Genres:** Music, Drama, History, War, Science Fiction.

#4. Peak Production Year
* The year **2020** stands out as the absolute peak year containing the most filmed and tracked movie records in this dataset.

---

#📂 File Structure
* `MovieDataAnalyticsNetflix.ipynb` - Core interactive notebook containing the full analysis code, pipeline execution, and data plots.
* `mymoviedb.csv` - Raw movie data input *(ensure this is uploaded or linked if applicable)*.

INSTALL DEPENDENCIES: 
pip install pandas numpy matplotlib seaborn

Open the notebook in Jupyter or VS Code:
jupyter notebook MovieDataAnalyticsNetflix.ipynb


THANK YOU ! 
