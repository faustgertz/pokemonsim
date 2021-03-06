# Introduction
My son loves Pokémon TCG (trading card game) a lot. At first, it was just about collecting the cards, but as he got older, and could read better, we started playing the game together, and I like it now too. Lately, I've heard him say things like, "I've just put together a new deck, and it is my best deck yet!" This made me think, how do you determine the best Pokémon deck? What makes a deck win more? Here are a few questions we can consider, and see if we can answer with data:

1. Can we predict a Pokémon subtype (e.g., Basic, Stage 1, Stage 2, etc.)?
2. Can we predict HP?
3. Can we predict type (e.g., Grass, Fire, Fighting, etc.)?
4. Is there a strongest type?
5. Can we build a winning-est deck?

# Set up
1. Please clone or download the zip from https://github.com/PokemonTCG/pokemon-tcg-data to your local git directory. This is an awesome database of Pokémon TCG.
2. Install MongoDB.
3. Run [init_cards_mongodb.py](database/init_cards_mongodb.py) to load the cards into MongoDB.
4. If you want to run the [analysis/nlp_eda.py](analysis/nlp_eda.py), then you'll need to download Senna tar file from [http://ronan.collobert.com/senna/](http://ronan.collobert.com/senna/), and extract to your home directory.

# Analysis	
Please see: [analysis.md](docs/analysis.md)

# Simulation
Please see: [simulation.md](docs/simulation.md)