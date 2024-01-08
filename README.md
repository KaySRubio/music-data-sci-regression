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
| Model                            | Best Hyperparameters            | Best mean accuracy score* |
| -----------                      | -----------                     | -----------               |
| Gradient Boosting                | max_depth: 3, n_estimators: 500 | 0.0666                    |
| Random Forest Regressor          | max_depth: 20, n_estimators: 100| 0.0773                    |
| Multivariate Linear Regression** | N/A                             | 0.0995                    |
| Multilayer Perceptron            | activation: logistic, hidden_layer_sizes: (50,) | 1.3223    |
* Mean accuracy score is how far off the model's predictions of danceability was from the actual danceability score. Danceability ranged from 0-1, so the best model was able to predict danceability of songs very close to the actual scores, only an average of 0.06 points off!
** Restricted set of predictors were used

## Python Libraries used:
[joblib](https://joblib.readthedocs.io/en/stable/)
[pandas](https://pandas.pydata.org/)
[matplotlib](https://matplotlib.org/)
[numpy](https://numpy.org/)
[seaborn](https://seaborn.pydata.org/)
[scikit-learn](https://scikit-learn.org/stable/)

## Testing the strongest model
The gradient boosting model with max-depth of 3 and number of estimators of 100 was used on 3 new songs
| Song name         | Artist      | Predicted Danceability | Actual Danceability |
| ----------------- | ----------- | -----------------------| --------------------|
| Wooden Ships      | Unknown     | 0.04867972             | 0.05166771          |
| Shakkei (Remixed) | Origamibiro | 0.51086412             | 0.44688061          |
| Niris             | Nicky Cook  | 0.83163573             | 0.94879937          |
Takeaways
  - Danceabilty ranges from 0-1 so these danceability predictions are pretty close!
  - Model agreed that Wooden Ships is not very danceable with a score of 0.0487 (actual: 0.0517)
  - Model agreed that Shakkei (Remixed) by Origamibiro is medium danceable with a score of 0.511 (actual 0.447)
  - Model agreed that Niris by Nicky Cook is super danceable with a score of 0.832 (actual 0.949)
  
  
