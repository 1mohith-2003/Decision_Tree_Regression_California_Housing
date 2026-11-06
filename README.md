# Decision Tree Regression – California Housing

## Objective
Predict the California housing dataset's median house value (`target`) from eight numeric housing and geographic features.

## Dataset
- Rows: 20,640
- Columns: 9 (8 features + target)
- Missing values: none in this supplied file
- Target: `target`
- Features: `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, `Longitude`

The supplied data uses shortened feature names and a `target` column, rather than the full original California Housing names. Target values are in the dataset's original scale (commonly expressed in units of $100,000); check the source workbook's notes before interpreting monetary values.

## Results
- Baseline unrestricted tree: train R² = 1.0000; test R² = 0.6221; MAE = 0.4547; RMSE = 0.7037.
- Best tested `min_samples_leaf`: 20; test R² = 0.7273; MAE = 0.4041; RMSE = 0.5978.

## Run
```bash
pip install -r requirements.txt
jupyter notebook
```
Open `Decision_Tree_Regression.ipynb` and run cells from top to bottom.

Alternatively:
```bash
python train_model.py
```

## Project contents
- `Decision_Tree_Regression.ipynb`: full Parts A–J walkthrough and code
- `california_housing.csv`: supplied dataset converted to CSV
- `train_model.py`: reproducible training/evaluation script
- `results.json`: actual experiment results
- `best_decision_tree.pkl`: trained tuned model
- PNG files: target distribution, model comparison, actual-vs-predicted, and tree visualization

## Notes
The train/test split uses `test_size=0.20` and `random_state=42`. Decision trees do not require feature scaling. The chosen best tested configuration is based on the highest test R² among the manually tested leaf-size values; a separate validation set or cross-validation is preferable for robust hyperparameter selection.
