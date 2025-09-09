# RecipeRater

## Overview
**RecipeRater** is a data science project that analyzes recipe data from Food.com to explore the relationships between nutrition, preparation complexity, and user ratings. The project applies data cleaning, exploratory data analysis (EDA), hypothesis testing, and machine learning to answer the question:

> *Which recipes offer the best balance between healthiness, quick preparation, and taste?*

This project was completed as part of coursework at UC San Diego by Ryan Lindberg and Ethan Haus.

📄 Full report: [RecipeRater Report](https://lindbergryan04.github.io/RecipeRater_report)

---

## Motivation
As busy students, our eating habits shifted toward convenience rather than health. We wanted to analyze real recipe data to identify recipes that are:
- Tasty (highly rated),
- Quick to prepare,
- Nutritionally balanced.

---

## Dataset
We used two Food.com datasets:
- **RAW_recipes.csv**: ~231k recipes with ingredients, nutrition, and steps.
- **RAW_interactions.csv**: ~1M user reviews with ratings and comments.

After merging and cleaning, we obtained a dataset of ~234k recipe records with features including:
- Ingredients, steps, and preparation time
- Nutrition (calories, protein, sugar, sodium, carbs, etc.)
- User ratings and reviews:contentReference[oaicite:1]{index=1}

---

## Key Analyses
- **Exploratory Data Analysis (EDA)**: Distribution of ratings, prep times, and correlations with nutrition.
- **Missingness Analysis**: Investigated review bias and missing ratings using permutation tests.
- **Balance Score**: Designed a custom metric combining health, time, and taste. Validated with hypothesis testing against human judgment (Pearson’s r = 0.51, p < 0.01).
- **Prediction Task**: Framed as a classification problem—predicting whether a recipe’s rating would fall into *Low, Medium, or High* categories.
- **Modeling**: Built and tuned a Random Forest classifier with feature engineering (log, squared, and interaction terms). Final model achieved ~58% accuracy (vs. 33% random baseline).
- **Fairness Analysis**: Checked performance disparities across rating categories, finding bias against medium-rated recipes.

---

## Tech Stack
- **Python** (pandas, NumPy, matplotlib, seaborn, scikit-learn, SciPy, plotly)
- **Statistical Testing**: Permutation tests, ANOVA F-tests
- **Machine Learning**: Random Forest Classifier, feature engineering, hyperparameter tuning with GridSearchCV
- **Visualization**: Matplotlib, seaborn, Plotly

---

## Results
- Most recipes are rated very highly (average 4.65/5) → rating bias exists.
- Prep time and nutrition show weak correlations with ratings.
- Balance score aligns moderately well with human intuition.
- Predicting ratings is challenging—nutritional and structural features alone don’t explain much variance.
- Models tended to overpredict “high” ratings due to skewed distribution.

---

