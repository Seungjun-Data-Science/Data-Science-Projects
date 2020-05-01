## Potential Gentrification Trends of New York City Airbnbs and Listing Price Prediction Using Machine Learning

This is the final project I did for my Math Senior Seminar on Data Science (MATH301)

#### Technology Stack, Libraries and Packages Used
- R, R-studio: library(tidyverse), library(ggthemes), library(GGally), library(ggExtra), library(caret), library(glmnet), library(corrplot), library(leaflet), library(kableExtra), library(RColorBrewer), library(plotly), library(tm), library(ggplot2), library(lubridate), library(lattice)
- Python: numpy, pandas, matplotlib, seaborn, geopandas, shapely, collections, sklearn

#### (1) Data Wrangling and Cleaning.Rmd
- Converted data types of each feature into appropriate ones (e.g. Features that are supposed to be numerical but encoded as categorical when I read the data ==> Change them to numerical)
- Merged 2016-2020 data sets into one big data
- Removed observations that had impossible prices (0 or negative values)
- Added average values of socioeconomic variables (e.g. unemployment level) of tracts for each borough (although these were not used in the final analysis)

#### (2) Initial Exploratory Data Analysis (EDA).Rmd
- Performed Exploratory Data Analysis on Price Distributions by room type in 2016-2020, Price Distributions by Neighborhood Group in 2016-2020, Number of listings by Room Type in 2016-2020, Number of listings by neighbourhood area in 2016-2020, and Number of Reviews v.s. Price
- Ran pairwise OLS regressions for [price ~ various room_type pairwise combinations for each year] and [price ~ various borough pairwise combinations for each year] to see if there were statistically signifcant differences in prices between different room types and boroughs and those differences changed over years.

#### (3) Additional EDA.ipynb
**- The outputs are not appearing on Github for some reason, so I leave the link for my original kernel/notebook ( https://www.kaggle.com/juminator/math301-final-project-more-eda )**
- Examining Luxurious Listings for each year (e.g. price > Q3 + IQR x 1.5), where they are mainly located and how that changes over time
- Number of Listings Map Visualization on a TRACT level over time
- Analysis on Minimum Revenue of each listing (= price x minimum number of nights x Demand (proxy: Number of Reviews)) + Which areas had the highest minimum revenue and was there any shift / change in those areas over time?

#### (4) Price Modelling Baseline (SLR, Ridge, Lasso, ElasticNet).ipynb
- Created additional Features from "listing name" column (e.g. average word length, word count etc.)
- Encoded Categorical Features into Numerical (one hot encoding) ==> Created dummy variables for all the categorical features
- Split the dataset into train (2016-2019 data) and test (2020) dataset 
- Created baseline models using linear regularized models (SLR, lasso, ridge, ElasticNet)
- Used 5 fold CV to evaluate performance and then tested on the 2020 dataset

#### (5) Price Modelling - HP Tuning Baseline Models and Blending them.ipynb
- Tuned hyperparameters using Python's RandomSearchCV and GridSearchCV
- Acquired really minimal increase in performance with the best parameters
- Simple blending (weighted averaging) increased performance a bit as well ( Lasso x 0.8 + Ridge x 0.15 + Elastic Net x 0.15 )

#### (6) Feature Selection with Lasso and Random Forest + Random Forest(RF) & GradientBoosting Baseline + RF Variations.ipynb
- Random Forest on entire dataset
- Random Forest Feature Importance ==> Feature Selection ==> Remove features with zero score for feature importance ==> RF on feature-selected data
- Blending (RF Baseline x 0.65 + Feature Selected RF with Feature Importance x 0.35)
- Feature Selection with Lasso Regression ==> Lasso, Ridge and Elastic Net Regression on Lasso feature-selected data
- Gradient Boosting Regression on entire dataset
- Feature Selection with Lasso Regression ==> RF on Lasso feature-selected data

#### (7) Increased n_estimators for RF, Feature Importance, XGboost, LGBM and Bagging on RF.ipynb
- RF with increased n_estimators (number of trees in the forest; increased from 50 to 300) on RF feature=selected data
- Permutation Feature Importance
- XGBoost and LGBM on RF feature-selected data
- Additional Bagging on Random Forest

There exist abundant literature which focused on various socioeconomic impact Airbnbs had on New York City such as gentrification until 2017. But not many papers examined how the gentrification scene looks in New York City since 2017. This paper aimed to fill that gap by analyzing data from 2016-2020 and pointing to areas with a high potential of gentrification. Moreover, I created statistical models predicting New York City Airbnb listing to beat predictive performance from previous research and to provide insights on which factors play a pivotal role in high or low listing prices. 

The main source of data comes from Inside Airbnb, an independent, non-commercial set of tools and data that allows users to explore how Airbnb is really being used in cities around the world.  According to the website, it is not associated with or endorsed by Airbnb or any of Airbnb's competitors. I collected 5 data sets from the website, each of them from year 2016 to 2020 respectively. In addition, I collected the Neighborhood Tabulation Areas (NTA) data . This data contains geospatial shape information that I needed to draw a map visualization on a more granular level.

Check out the final paper and presentation slides!
