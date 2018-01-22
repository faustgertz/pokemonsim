# Introduction
My son loves Pokémon TCG (trading card game) a lot. At first, it was just about collecting the cards, but as he got older, we started playing the game together, and I like it now too. Lately, I've heard him say things like, "I've just put together a new deck, and it is my best deck yet!" This made me think, how do you determine the best Pokémon deck? What makes a deck win more? Here are some questions I want to answer with data:

1. Can we predict a Pokémon subtype (e.g., Basic, Stage 1, Stage 2, etc.)?
2. Can we predict HP?
3. Can we predict type (e.g., Grass, Fire, Fighting, etc.)?
4. Is there a strongest type?
5. Can we build a winning-est deck?

## Set up
1. Please clone or download the zip from https://github.com/PokemonTCG/pokemon-tcg-data to your local git directory. This is an awesome database of Pokémon TCG.
2. Install MongoDB.
3. Run ```database/init_cards_mongodb.py``` to load the cards into MongoDB.

# Questions

## What does the data look like?
See ```analysis/exploratory_data_analysis.ipynb```.

## Can we classify a Pokémon Subtype?

A Pokémon subtype falls into one of:

```
['BREAK' 'Basic' 'EX' 'GX' 'LEGEND' 'Level Up' 'MEGA' 'Restored' 'Stage 1'
 'Stage 2']
```
 
As a warmup exercise to our goal of creating the best deck, here is a question: Given some features of a Pokémon card, can we predict it's subtype?

To transform our data into a tabular format, run: ```utilities/build_subtype_dataset.py```

To answer the question, I built several classifiers, and then also an ensemble voting classifier, in file: ```analysis/predict_subtype.py```

Results were decent, but not super:

```
Accuracy: 0.87 (+/- 0.05) [Support Vector Machine]
Accuracy: 0.88 (+/- 0.04) [Random Forest]
Accuracy: 0.84 (+/- 0.07) [Multi-Layer Perceptron]
Accuracy: 0.89 (+/- 0.05) [Voting Ensemble]
```

## Can we predict HP?

Another thing we can attempt with this data set is to predict HP given values for Weakness total, Retreat Cost, Total of all Attack Energy Costs. Even though HP are in increments of 10, we will consider them as continuous, when building a regression model in ```analysis/predict_hp.py```.

Using R squared and MSE, we can evaluate a few different models:

```
R squared: 0.86, MSE: 86.22, [Linear Regression]
R squared: 0.86, MSE: 88.13, [Gradient Boosting Regressor]
R squared: 0.86, MSE: 87.59, [Support Vector Regression]
```

These are very close, with Linear Regression giving the best model.