# Vassar College MATH 347 - Bayesian Inference Final Project

### Data
- Player and Team Data from past 2 seasons from Basketball Reference 
- Instagram Follower Count: Python Scraper (e.g. BeautifulSoup)
- Variables / Features (46 variables: All Numerical) 

### Part I
- Implement and observe how “Naive Bayes algorithm”, a Bayesian algorithm which uses the Bayes rule, works in practice with real world dataset (NBA Dataset)
- Test if Naive Bayes works well with our NBA Player dataset (e.g. accuracy, f1-score) and also in comparison to other classification algorithms
- See which factors / features are influential in determining which player becomes an all-star player

### Part II
- Inference Question: Do players in certain positions (e.g. Center, Guard, Forward) have more instagram followers, on average, than those in other positions?
How do prior and posterior distributions compare to each other?
- How do we choose priors? Which model should we use?
- If we use the hierarchical model, for which position is the shrinkage / pooling effect the most prominent? What does this mean?

### Jupyter Notebooks
- Wrangling and Cleaning Basketball Reference Data.ipynb: Cleaning and Wrangling Data. Python BeautifulSoup Scraper to collect instagram follower numbers from instagram.com for 81 major NBA Players
- Naive Bayes Model.ipynb: Comparison of performance amongst Gaussian Naive Bayes model, Guassian Naive Bayes Model with highly correlated features removed (feature independence), Logistic Regression and Decision Tree Classifier. Identified top 5 important features by choosing the five features with highest variability within each class (y=1 / y=0).
- NBA_IG.Rmd: Using R to build a hierarchical model for Mean Instagram Follower Number for the three groups by position (Center, Guard, Forward). ($\mu_j$ where j = guard, center, forward) 

### Presentation
https://docs.google.com/presentation/d/1WgdCvdtnukjMxM8vDhxdvUKwMmZ_XnRh39EPnDH8dnU/edit?usp=sharing
