# Stock Price Prediction using Stacked LSTMs (AAPL Dataset)

## 📜 Description

An end-to-end time-series project predicting AAPL stock closing prices using stacked LSTMs with TensorFlow/Keras. This repository covers the full workflow: data acquisition (Tiingo API/CSV), EDA, MinMax scaling, model building, training, RMSE evaluation, and 30-day autoregressive forecasting.



## ✨ Features

* **Data Acquisition**: Fetches historical stock data from CSV (originally from Tiingo API using `pandas_datareader`).
* **Exploratory Data Analysis (EDA)**: Visualizes price history and volume, checks for missing data.
* **Preprocessing**: Scales data using `MinMaxScaler` and creates time-step sequences for LSTM input.
* **Model Building**: Implements a Stacked LSTM model (3 layers) using TensorFlow/Keras.
* **Training & Evaluation**: Trains the model and evaluates performance using Root Mean Squared Error (RMSE) on the original price scale.
* **Forecasting**: Predicts the next 30 days of stock prices using an autoregressive approach.
* **Visualization**: Plots training/validation loss, model predictions vs. actual data, and the 30-day forecast.

## 📊 Dataset

This project uses historical daily stock data for Apple (AAPL). The data includes columns like `date`, `open`, `high`, `low`, `close`, and `volume`. The primary target variable for forecasting is the `close` price.

* The included `AAPL.csv` file contains data up to May 22, 2020 (originally fetched from Tiingo).
* The code includes a fallback to fetch data using the Tiingo API via `pandas_datareader` if the CSV is not found (requires a Tiingo API key).

## ⚙️ Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd <your-repo-name>
    ```
2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```
3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(You'll need to create a `requirements.txt` file listing the libraries below)*

## 🚀 Usage

1.  **Ensure you have the `AAPL.csv` file** in the root directory, or **add your Tiingo API key** in the notebook (Cell 5) if you want to fetch fresh data.
2.  **Open and run the Jupyter Notebook:** `model.ipynb`
    ```bash
    jupyter notebook model.ipynb
    ```
    Run the cells sequentially from top to bottom.

## 📈 Results

* The model learns the general trend of the AAPL stock price.
* The evaluation resulted in a **Train RMSE** of approximately **$2.65 USD** and a **Test RMSE** of approximately **$6.65 USD** (*Note: Replace these with your actual results after running the notebook*).
* A 30-day price forecast is generated and visualized.



## ⚠️ Limitations & Future Work

* **Not Financial Advice**: This model is for educational purposes and should not be used for actual trading decisions. It only considers historical closing prices.
* **Model Lag**: Like many time-series models based solely on past data, the predictions tend to lag behind sharp price changes.
* **Future Work**:
    * Incorporate more features (Volume, Open, High, Low, technical indicators).
    * Add sentiment analysis from financial news.
    * Perform hyperparameter tuning (e.g., using KerasTuner).
    * Experiment with other models (e.g., Prophet, ARIMA, Transformers).

## 📦 Dependencies

* pandas
* pandas-datareader
* numpy
* matplotlib
* scikit-learn
* tensorflow

*(Create a `requirements.txt` file with these library names)*
