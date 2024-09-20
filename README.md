# NFL Bet Outcome Prediction Models

## Project Objective

The objective of this project is to leverage machine learning techniques to predict various bet outcomes for NFL games. The project aims to develop three distinct binary classification models that will predict: 

1.) whether the favorite team will win or lose a game

2.) whether the favorite team will cover the spread

3.) whether the total points scored in a game will be over or under the given threshold

By utilizing advanced data preprocessing methods, feature selection techniques, and robust classification algorithms, this project seeks to enhance the accuracy and reliability of these predictions. The ultimate goal is to provide data-driven insights and probabilistic assessments to support informed betting decisions on NFL moneyline, spread, and over/under bets.

I used Python and Jupyter Notebooks for all stages of this project. 

## Project Description

I am very interested the NFL and sports betting, so what better project to undertake than trying to maximize my profit while betting on NFL games. There are 3 main bet types for any given NFL game:

### Moneyline 
Moneyline betting is the simplest form of betting on sports. In a moneyline bet, you are simply betting on which team will win the game outright, regardless of the score. For example, if the moneyline odds for Team A are -150 and for Team B are +130, a $150 bet on Team A would win $100, while a $100 bet on Team B would win $130. Historically in the NFL, the favorite wins ~67% of the time.

### Spread Betting
Spread betting involves betting on the margin of victory in a game. A point spread is set by oddsmakers to level the playing field between two teams. For example, if Team A is favored by 7 points (-7) against Team B, they must win by more than 7 points for a bet on Team A to pay out. Conversely, if you bet on Team B (+7), they must either win the game outright or lose by fewer than 7 points for the bet to be successful. If the game ends exactly on the spread, the bet is a push and the wager is refunded. Spread odds are usually always around 50%.

### Over/Under Betting
Over/Under betting involves betting on the total number of points scored by both teams combined in a game. Oddsmakers set a projected total, and bettors can choose to bet on whether the actual combined score will be over or under this number. For example, if the over/under for a game is set at 45 points, and the final score is 28-20 (totaling 48 points), bets on the over would win, while bets on the under would lose. Over/Under odds are usually around 50%. 

## Project Process

The steps I took during this project are as follows:

### 1.) Data Collection

I was able to export some data from online, however I had to use various web scraping methods to collect historical NFL bet data and player/team ratings.

### 2.) Data Cleaning

After collecting all of my data, I needed to clean it. This involved imputing missing values, correcting unusual values, transforming data into a more standard and useful format, etc.

Since most of my data came from different sources I also had to merge all of the data into a master data frame

### 3.) Feature Creation/Engineering

I broke this step into 3 stages:

1.) I created features that I felt better represented the strentgh of teams offense and defense, as well as various other team strength and situational metrics.

2.) Needed to lag the features from step 1 (and some other features). This is due to the fact that for a given week n, I had stats through that given week. For a prediction model, it needs to be trained on data for week n-1. For example, if I want to predict whether the favorite in week 3 will cover the spread, I cannot have data on the week 3 game that has already happened. It needs to have data through week 2

This stage also entailed some data imputation.

3.) Here I created additional and aggregate features that I thought might be useful for our model. The goal was to create features that aggregated some of the other features so that later on we wouldn't run into the issue that arise from multicollinearity and so on.

### 4.) Feature Selection

Used various feature selection methods to select the best features to train our model on. I wanted my models not have to many features (keep it simple). I used these different feature selection techniques on both scaled and unscaled data depending on the models that I wanted to train the data on.

### 5.) Modeling

Here I created models for each NFL bet type. I created models for unscaled and scaled data. For the scaled data, I tried different scaling methods and I created models for the different scaling methods.

## Conclusions

The main goal of this project was for to get some basic experience in data collection, cleaning, feature creation, and the process of training some classical machine learning models for a binary classification problem. I know that there are much more efficient and technical ways to train these models and evaluate them, however this project was meant to be an introduction for me in this space. With that being said, I found some interesting and useful models for predicting some of our bet outcomes:

### 1.) Moneyline

No model gave me the accuracy that would be better than just picking the favorite in a given NFl game.

### 2.) Spread

Many models were useful for predicing if the favorite would cover the spread. They ranged from KNN to XGB Classifiers, with some models reaching an accuracy of 57%!

### 3.) Over/Under

Some models were useful in predicting whether the over would hit for a given game. Some of the performance metrics for these moels were not great, even though they had high accuracy, but the accuracy was around 55%.

## Implications & Next Steps

By reading through this there are many issues from cleaning, transforming, data imputation, feature creation, and so on. Like I mentioned this was my first try at trying to work through the development of a machine learning model. 

I will be updating periodically with changes to any of the aforementioed issues.

The next steps for this project would be:

- Create/collect more interesting features as there are so many advanced NFL statistics that have gained prominence in recent years due to the fact that they provide better insights into performance

- Fine-Tune models

- Play around with different feature selection, scaling, model parameters, etc

- Creating a pipeline so that I can use data for the current 2024 NFL season to make predictions









