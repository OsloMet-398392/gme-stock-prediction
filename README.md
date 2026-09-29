# GameStop Stock Price Prediction

This project was created for **Mandatory Assignment 2: Machine Learning**.

The goal of the project is to use historical GameStop stock data to predict the closing price of the stock for a given date.

## Group members

- odamu0185
- nebro9110

## Use case

The selected use case is predicting the historical closing price of GameStop stock.

The model receives a date as input and returns a predicted closing price in US dollars.

## Dataset

The project uses the `GME_stock.csv` dataset from Kaggle:

**GameStop Historical Stock Prices**

The CSV file must be placed in the following location:

```text
data/GME_stock.csv
```

The dataset is not included in this GitHub repository. Each group member must download the dataset and place it in the `data` folder.

## Machine-learning algorithm

We chose **Linear Regression** because the target variable, closing price, is a continuous numerical value.

The date is converted into the number of days since the first date in the dataset. Linear Regression is simple, easy to understand, and suitable for demonstrating the basic machine-learning workflow.

Stock prices are complex and volatile, so this model is intended as an educational example rather than a reliable financial forecasting tool.

## Project contents

The Jupyter Notebook includes:

- Loading and inspecting the dataset
- Cleaning and preparing the data
- Visualizing historical closing prices
- Converting dates into numerical values
- Chronological train-test split
- Training a Linear Regression model
- Predicting closing prices
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² score
- Price-category accuracy
- Confusion matrix
- A function for predicting the price on a specific date

## Project structure

```text
gme-stock-prediction/
├── data/
│   ├── .gitkeep
│   └── GME_stock.csv
├── .gitignore
├── GME_stock_prediction.ipynb
├── README.md
├── pyproject.toml
└── uv.lock
```

The file `GME_stock.csv` is stored locally and is ignored by Git.

## Requirements

The project uses Python and the following packages:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- jupyter
- ipykernel

The dependencies are managed with `uv`.

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/USERNAME/gme-stock-prediction.git
```

Replace `USERNAME` with the GitHub username of the repository owner.

Move into the project folder:

```bash
cd gme-stock-prediction
```

### 2. Install the dependencies

Make sure `uv` is installed, and then run:

```bash
uv sync
```

This creates the virtual environment and installs the dependencies specified in `pyproject.toml` and `uv.lock`.

### 3. Add the dataset

Download `GME_stock.csv` from Kaggle and place it here:

```text
data/GME_stock.csv
```

### 4. Start JupyterLab

```bash
uv run jupyter lab
```

Open the following notebook:

```text
GME_stock_prediction.ipynb
```

### 5. Run the notebook

In JupyterLab, select:

```text
Kernel → Restart Kernel and Run All Cells
```

Make sure all cells run without errors.

## Model evaluation

Because this is a regression problem, the main evaluation metrics are:

- **MAE:** Average prediction error measured in dollars
- **RMSE:** Prediction error that gives more weight to large errors
- **R²:** How much of the variation in stock prices is explained by the model

A confusion matrix is normally used for classification, not regression. To satisfy the assignment requirements, the actual and predicted prices are also divided into three categories:

- Low
- Medium
- High

The category predictions are evaluated using an accuracy score and a confusion matrix.

## Making a prediction

The notebook contains a function named:

```python
predict_price(date_string)
```

Example:

```python
predicted_price = predict_price("2021-01-28")
print(f"Predicted closing price: ${predicted_price:.2f}")
```

The date must use the following format:

```text
YYYY-MM-DD
```

## Important limitations

The model only uses the date as its input feature. It does not consider trading volume, company news, market conditions, financial reports, or other factors that may affect stock prices.

Linear Regression also assumes a relatively simple relationship between time and price. GameStop's stock price has experienced large and sudden changes, which a simple linear model cannot represent accurately.

The project is therefore intended to demonstrate a basic machine-learning workflow and should not be used to make financial decisions.

## Disclaimer

This project was created for educational purposes only. It is not financial advice, and the predictions should not be used for investing or trading.