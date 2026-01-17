# IMDb Movies: A Data Science Exploration

This repository contains a comprehensive data analysis of IMDb movie records, exploring the intricate relationships between audience reception, critical acclaim, financial performance, and genre trends. This project was developed as part of the **CSMODEL** course at **De La Salle University**.

## Project Overview

The core objective of this study is to identify what drives a movie's success on IMDb. Success is measured through multiple lenses: audience popularity (vote counts), critical reception (Metascore), and internal audience satisfaction (IMDb Rating).

The dataset, sourced from Kaggle, includes over 6,000 cleaned records of movies that have achieved significant audience engagement (minimum 25,000 votes). By analyzing metadata such as genres, budget, gross earnings, and cast members, the project uncovers patterns in the film industry across different decades.

## Authors

**De La Salle University - Manila**

* **Mikaela Amon**
* **John Maverick Cisneros**
* **Chynna Mae Tria**
* **Edson Willie**
* **Justin Vilbar**

---

## Research Questions

The analysis seeks to answer several key questions regarding the film industry:

1. **Financial Impact:** How do budget and gross earnings correlate with audience ratings and popularity?
2. **Genre Trends:** Which genres consistently receive the highest ratings versus the highest number of votes?
3. **Critical vs. Public Opinion:** What is the correlation between professional critic scores (Metascore) and public ratings (IMDb Rating), and how has this relationship evolved by decade?
4. **Star Power:** Does the presence of top-billed actors significantly impact a movie's reach and reception?

---

## Technical Methodology

### 1. Data Cleaning & Preprocessing

To ensure statistical integrity, the notebook performs rigorous data cleaning:

* **Handling Missing Values:** Critical columns like `metascore` and `gross` were processed to handle null values without biasing the results.
* **Type Enforcement:** Significant effort was placed on resolving `AttributeError` issues by forcing columns into numeric types using `pd.to_numeric(errors='coerce')` to handle dirty data strings (e.g., commas in vote counts).
* **Decade Segmentation:** A `period` feature was engineered to group movies into 10-year intervals for longitudinal analysis.

### 2. Statistical Analysis

The project employs various statistical methods to validate findings:

* **Pearson Correlation:** Used to measure the linear relationship between variables (e.g., Rating vs. Votes).
* **SciPy Integration:** To bypass internal Pandas/NumPy version conflicts, `scipy.stats.pearsonr` was utilized for robust correlation calculations across different eras.
* **Variance Checking:** Implementation of standard deviation checks to ensure correlation is only calculated on statistically viable data groups.

### 3. Data Visualization

Key insights are presented through:

* **Heatmaps:** To visualize the correlation matrix across all numeric features.
* **Grouped Bar Charts:** Comparing IMDb Ratings and Metascores across decades.
* **Scatter Plots:** Visualizing the relationship between financial success and audience reach.

---

## Key Insights

* **Popularity vs. Quality:** The analysis reveals that financial success (gross earnings) is a much stronger predictor of a movie's **popularity** (total votes) than its **average rating**.
* **The "Blockbuster" Effect:** Highly popular genres like Action and Adventure dominate in terms of vote counts and gross earnings, but Drama consistently holds higher average ratings.
* **Star Power Influence:** While the presence of prolific, top-billed actors is strongly associated with higher vote counts (marketing draw), it does not guarantee a higher IMDb rating, suggesting that "Star Power" drives reach but not necessarily satisfaction.
* **Critics vs. Fans:** The correlation between Metascore and IMDb ratings has fluctuated over the decades, reflecting changing dynamics between professional criticism and audience sentiment.

---

## Technologies Used

* **Python 3.x**
* **Pandas:** Data manipulation and analysis.
* **NumPy:** Numerical computing and array handling.
* **Matplotlib / Seaborn:** Data visualization.
* **SciPy:** Advanced statistical calculations.
* **Jupyter Notebook:** Interactive development environment.

## How to Run

1. Ensure you have Python installed.
2. Install the required libraries:
```bash
pip install pandas numpy matplotlib seaborn scipy
```

3. Open `CSMODEL_Group_6.ipynb` in Jupyter Notebook or Google Colab.
4. Upload the IMDb dataset (ensure the filename matches the path in the script).
5. Run all cells to generate the analysis and visualizations.
