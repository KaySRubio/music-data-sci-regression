# Predicting Danceability using Machine Learning

##Goal
Train a model that predicts danceability from the temporal features of songs.

## Data
Metadata on 13,000 songs from EchoNest (now Spotify), a subset of the [Free Music Archive](https://github.com/mdeff/fma). Features include 223 temporal features, along with instrumentalness and tempo.
### Dataset Citation: 
@inproceedings{fma_dataset,
  title = {{FMA}: A Dataset for Music Analysis},
  author = {Defferrard, Micha\"el and Benzi, Kirell and Vandergheynst, Pierre and Bresson, Xavier},
  booktitle = {18th International Society for Music Information Retrieval Conference (ISMIR)},
  year = {2017},
  archiveprefix = {arXiv},
  eprint = {1612.01840},
  url = {https://arxiv.org/abs/1612.01840},
}

## Results
| Model      | Best Hyperparameters| Best mean accuracy score*
| ----------- | ----------- |
| Gradient Boosting      | max_depth: 3, n_estimators: 500       | 0.0666
| Random Forest Regressor   | max_depth: 20, n_estimators: 100        | 0.0773
