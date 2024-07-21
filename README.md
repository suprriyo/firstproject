# Gemstone Price Prediction

## Introduction About the Data
The goal is to predict the price of a given diamond (Regression Analysis).

### Independent Variables
- **id**: Unique identifier of each diamond
- **carat**: Carat (ct.) refers to the unique unit of weight measurement used exclusively to weigh gemstones and diamonds.
- **cut**: Quality of Diamond Cut
- **color**: Color of Diamond
- **clarity**: Diamond clarity is a measure of the purity and rarity of the stone, graded by the visibility of these characteristics under 10-power magnification.
- **depth**: The depth of the diamond is its height (in millimeters) measured from the culet (bottom tip) to the table (flat, top surface)
- **table**: A diamond's table is the facet that can be seen when the stone is viewed face up.
- **x**: Diamond X dimension
- **y**: Diamond Y dimension
- **z**: Diamond Z dimension

### Target Variable
- **price**: Price of the given Diamond.

For more details, check this link: [American Gem Society](https://www.americangemsociety.org)

## Approach for the Project

### 1. Data Ingestion
- The data is first read as CSV.
- The data is split into training and testing sets and saved as CSV files.

### 2. Data Transformation
- A `ColumnTransformer` Pipeline is created.
  - For Numeric Variables: `SimpleImputer` with median strategy, followed by `StandardScaler`.
  - For Categorical Variables: `SimpleImputer` with the most frequent strategy, followed by ordinal encoding, and then `StandardScaler`.
- The preprocessor is saved as a pickle file.

### 3. Model Training
- Base models are tested, with the best being the CatBoost Regressor.
- Hyperparameter tuning is performed on CatBoost and KNN models.
- A final `VotingRegressor` is created, combining predictions of CatBoost, XGBoost, and KNN models.
- This model is saved as a pickle file.

### 4. Prediction Pipeline
- Converts given data into a dataframe and has various functions to load pickle files and predict the final results in Python.

### 5. Flask App Creation
- A Flask app is created with a User Interface to predict gemstone prices inside a Web Application.

---

If you continue to encounter issues, try using `git pull --rebase` or `git push --force` commands as mentioned earlier with caution. If you have any other questions, feel free to ask!
