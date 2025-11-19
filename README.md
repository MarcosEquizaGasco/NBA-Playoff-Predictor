# NBA-Playoff-Predictor

A machine learning project to predict how far teams will go in the NBA Playoffs based on season-level data extracted from [Basketball-Reference](https://www.basketball-reference.com/).

## Overview  
This project uses historical data from the NBA regular season and playoff seeds/outcomes to train predictive models, with the goal of forecasting how far teams will advance in the playoffs for the 2022-2023 season. This is a class project demonstrates use of data scraping/collection, preprocessing, modeling, evaluation, and results visualization.


## Key Components  
1. **Data Collection/Scraping**  
   - The notebook `ScrapingData.ipynb` pulls historical statistics (per_100, advanced, and shooting statistics tables) for each team per season.  

2. **Data Preprocessing & Feature Engineering**  
   - `ScrapingData.ipynb` also handles missing values, transforms features (e.g., win percentage, pace, offensive/defensive stats), and scales or normalizes features.  
   - It defines the target variable, a Playoff score from zero to one, where zero represents not making the Playoffs, and one represents the team played in the championship that year. The numbers between that (0.25, 0.50, 0.75) signify how far in the playoffs that specific team reached. Therefore, if our model gives a team in the 2023 season a higher number, they are more likely to make it to the championship.
     
3. **Modeling & Evaluation**  
   - Three models (Multiple Regression, K-Nearest Neighbors, and Random Forest Regression) are trained on historical data.  
   - The models are evaluated on the 2022-2023 season to estimate how well they predict final Playoff standings. 

4. **Results & Visualizations**  
   - A Playoff bracket for each model was created, with the 2022-2023 initial seedings. Then, the team with the higher predicted Playoff score for each matchup advanced to the next round. The team with the highest number would eventually go on to win the 2023 NBA Finals.
   - The brackets are named after the model for which they were created.
     
## Key Findings

1. The win percentage (or overall record) remains by far the strongest predictor of playoff qualification.

2. The predictive accuracy may vary by conference (East vs West) or across seasons with play-style changes, such as the heavy reliance on 3-point shooting in the last decade. 

## Future Directions
Incorporate more granular features (player-level stats, injury reports, strength of schedule).

Add ensemble methods or hyperparameter tuning to improve model performance.

Deploy a simple web app or interactive dashboard where a user selects a season to simulate.

Update model yearly and track performance drift over seasons.


