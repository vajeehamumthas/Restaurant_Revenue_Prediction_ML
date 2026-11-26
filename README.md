# Restaurant Revenue Prediction (Machine Learning)

A regression project that predicts a restaurant's **revenue** from its characteristics, comparing five machine learning models.

## Objective
- Estimate the continuous Revenue value from 15 restaurant features
- Compare Linear Regression, Decision Tree, Random Forest, KNN and SVR on the same train–test split
- Choose the best model using R², Mean Absolute Error (MAE) and Mean Squared Error (MSE)

## Dataset
- **File:** `restaurant_data.csv`
- 8,368 restaurants, 17 columns, no missing values and no duplicate rows
- **Categorical:** Location, Cuisine, Parking Availability
- **Numeric:** Rating, Seating Capacity, Average Meal Price, Marketing Budget, Social Media Followers, Chef Experience Years, Number of Reviews, Avg Review Length, Ambience Score, Service Quality Score, Weekend Reservations, Weekday Reservations
- **Target:** Revenue
- `Name` is only an identifier, so it was dropped, which leaves 15 features

## Tools
Python, pandas, scikit-learn, Google Colab

## Method
1. Inspect the data (nulls, duplicates)
2. Drop the `Name` column
3. Encode Location, Cuisine and Parking Availability with LabelEncoder
4. Split 80% train (6,694 rows) and 20% test (1,674 rows), `random_state=24`
5. Scale features with StandardScaler for the distance-based models (KNN and SVR)
6. Train the five models and evaluate them

## Results
| Model | Train R² | Test R² | MAE | MSE |
|---|---|---|---|---|
| Linear Regression | 0.9576 | 0.9596 | 41,483 | 3,023,048,845 |
| Decision Tree | 1.0000 | 0.9966 | 12,331 | 255,135,936 |
| **Random Forest** | **0.9999** | **0.9991** | **6,378** | **67,558,863** |
| KNN | 0.9220 | 0.8869 | 70,550 | 8,453,383,552 |
| SVR (linear kernel, C=100) | 0.9284 | 0.9280 | 49,580 | 5,385,650,106 |

**Best model: Random Forest**, with a test R² of 0.9991 and an average error of about 6,378 on the 1,674 test restaurants.
Decision Tree and Random Forest results change slightly between runs.

## Limitations and future work
- The very high scores suggest the dataset may be clean or synthetic, so results on real-world data may be lower
- Next steps: hyperparameter tuning, cross-validation, feature-importance analysis and deploying the model as a prediction app

## How to run
1. Open `Restaurant_Revenue_Prediction.ipynb` in Google Colab
2. Upload `restaurant_data.csv` and change the file path in the `pd.read_csv(...)` cell to match
3. Run all cells

## Files
| File | Description |
|---|---|
| `Restaurant_Revenue_Prediction.ipynb` | The notebook: preprocessing, model training and evaluation |
| `restaurant_data.csv` | The dataset |
| `Restaurant_Revenue_Prediction_final.pptx` | The project presentation |

## Author
Vajeeha Mumthas PV
[LinkedIn](https://linkedin.com/in/vajeeha-undefined-169594438) | [GitHub](https://github.com/vajeehamumthas)
