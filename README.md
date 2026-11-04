# Housing price regression by Michelle Jiang and Cici Meng

A scikit learn regression project that extends the assigned housing notebook. This project uses housing data to build a regression model that predicts sale prices. Us as a team, we explored how features such as overall quality, square footage, etc. relates to a home’s value. We used the training data to build and evaluate models before predicting prices for the test houses and submitting our results to Kaggle.
We started with a simple linear regression model using only overall quality. From there, we added more features and converted categorical variables into a format the models could use. We organized these steps into scikitlearn pipelines and used cross validation to compare models by (RMSE).

## Files

- `sample_housing_prediction.ipynb`: original assignment structure, corrected examples, process commentary, and code reproducing the best submitted model.
- `submission_improved.csv`: final selected submission, with the lowest confirmed Kaggle RMSE.
- `submission_v4.csv`: later submitted experiment that performed worse.
- `submitted_results.csv`: recorded Kaggle results.
- `requirements.txt`: Python dependencies.

## Run

Install dependencies using `pip install -r requirements.txt`, then open the notebook in Jupyter or Google Colab. Download the updated competition files and put `train.csv`, `test.csv`, and `sample_soln.csv` in the notebook folder (upload through the Files sidebar in Colab). Run all cells; comparison takes several minutes. The final cell writes `submission_improved.csv` with columns `Id,SalePrice`.

## Process and submitted results

Start with the assigned OverallQual example, then add imputation, ordinal and one-hot encoding, and pipelines. Compare models using five-fold dollar RMSE, with preprocessing fitted inside each fold. The final selected model blends log-target Huber gradient boosting (70%) with dollar-target extra trees (30%). It had validation RMSE 27,924.49 and the lowest confirmed Kaggle RMSE among our submissions.

| Submission | Kaggle RMSE |
| --- | ---: |
| Original Ridge | 161,049.15525 |
| Improved tree blend aka final selected model | **36,105.15526** |
| V4 regression blend | 59,376.14456 |

The later V4 model had lower validation RMSE but worse Kaggle performance. We retained the best confirmed Kaggle submission. Rare extreme houses, repeated model comparisons, and differences between validation and leaderboard samples limit how accurately validation predicts Kaggle results.
