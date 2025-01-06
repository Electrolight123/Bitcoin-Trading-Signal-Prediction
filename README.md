# Bitcoin Trading Signal Prediction Using Machine Learning Models

## Introduction

Bitcoin trading involves the buying and selling of Bitcoin in hopes of profiting from its price fluctuations. As the first and most widely recognized cryptocurrency, Bitcoin operates on a decentralized digital ledger called blockchain, which records all transactions transparently and securely. Unlike traditional currencies issued by central banks, Bitcoin is decentralized, governed by its users and a public, cryptographically secure network.

Bitcoin's value is highly volatile, influenced by factors like market sentiment, regulatory news, technological advancements, and macroeconomic conditions. This volatility creates opportunities for traders to capitalize on price movements, whether by buying low and selling high or by speculating on price drops. However, it also introduces considerable risk, making trading both challenging and potentially rewarding.

### Project Goal

The goal of this project is to predict **buy/sell trading signals** for Bitcoin based on historical price data. The method involves using machine learning models to classify trends and optimize strategy.

---

## Data Overview

- **Source**: Bitstamp Bitcoin price data
- **Variables**: Timestamp, Open, High, Low, Close, Volume (BTC and Currency), Weighted Price
- **Sample Size**: ~2.8 million minute-by-minute observations

---

## Role of Machine Learning in Bitcoin Trading

- Machine learning has emerged as a valuable tool in Bitcoin trading, allowing traders to use past price data, market indicators, and other variables to train models that predict potential price movements. 

- By incorporating indicators such as moving averages, momentum oscillators, and volatility measures, machine learning models can help identify trends and trading signals.These models are particularly useful in a volatile market like Bitcoin, where price patterns and trends can change quickly.

---

## Technical Analysis and Indicators

Technical analysis relies on historical prices and volume to predict future price movements, utilizing indicators that represent:

- **Momentum**: Indicators like the Relative Strength Index (RSI) and Rate of Change (ROC) signal overbought or oversold conditions by examining recent price changes.
- **Trend**: Moving averages (simple and exponential) smooth out price fluctuations, helping to identify trends.
- **Volatility and Reversal Signals**: Stochastic oscillators gauge the probability of trend reversals by comparing closing prices within a defined range of prices over a period.

### Creating the Target Variable (Classification Problem)

- **Buy/Sell Signals**: Binary labels (1 for buy, 0 for sell) based on short-term and long-term price relationships.
- **Moving Averages for Labeling**: Short-term (10-day) and long-term (60-day) moving averages are used:
  - If the short-term moving average is above the long-term average, it signals an uptrend (1).
  - If the short-term moving average is below the long-term average, it signals a downtrend (0).

---

## Feature Engineering

Momentum Indicators:
- **RSI**: Measures the speed and change of price movements, signaling potential reversals when above 70 (overbought) or below 30 (oversold).
- **ROC**: Percentage change over a fixed period, indicating acceleration or deceleration in price.

Trend Indicators:
- **Moving Averages (MA)**: Simple and exponential moving averages reduce noise and highlight trends.
- **Stochastic Oscillator**: Measures closing prices relative to a price range, generating reversal signals.

### Why These Indicators?

These indicators represent essential aspects of price behavior:
- **RSI and ROC**: Capture price momentum, helping detect reversals.
- **Stochastic Oscillator**: Tracks trend strength and exhaustion points.
- **Moving Averages**: Identify directional price trends.

---

## Model Selection

### Problem Type
Classification (binary labels for buy/sell decisions).

### Model Types Considered

- **Linear Models**:
  - Logistic Regression and Linear Discriminant Analysis: Simple, interpretable models that work well if relationships are linear.

- **Nonlinear Models**:
  - K-Nearest Neighbors and Decision Tree: Capture more complex relationships but may overfit.

- **Ensemble Methods**:
  - Random Forest, AdaBoost, Gradient Boosting: Offer greater robustness and capture nonlinearity by combining multiple decision trees.

### Random Forest Selection
Random Forest was chosen due to its ability to:
- Manage high-dimensional data.
- Be resilient to overfitting.
- Deliver robust performance in non-linear scenarios.

---

## Backtesting the Strategy

### Backtesting Goal
Evaluate how well the model would perform in actual trading scenarios.

### Process
- Calculate returns based on predicted signals.
- Compare them to actual market returns.

### Cumulative Returns Visualization
A cumulative return chart for model-predicted vs. actual returns highlights model effectiveness and risk-adjusted performance.

---

## Results

- **Model Performance**: The Random Forest classifier achieved the highest accuracy on the validation set.
- **Backtesting**: Demonstrated the effectiveness of the strategy in capturing market trends and generating profitable returns.

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/Bitcoin-Trading-Signal-Prediction.git
   cd Bitcoin-Trading-Signal-Prediction

2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt

3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook /Bitcoin_Trading_Signal_Analysis.ipynb

4. Run the cells step-by-step to perform the analysis and evaluate the model.

---

## Acknowledgments

### Acknowledgments

- **Dataset**: The dataset is sourced from the Bitstamp Bitcoin price data, which provides valuable historical price data for Bitcoin trading.  
- **Libraries**: Technical indicators and machine learning models are implemented using the following Python libraries:
  - **Pandas**: For data manipulation and analysis.
  - **NumPy**: For numerical operations and handling arrays.
  - **Scikit-learn**: For implementing machine learning models and evaluation.
  - **Matplotlib**: For data visualization and plotting.

---

### Images

- **Model Performance Visualization**: Includes a **cumulative returns chart** comparing model-predicted returns versus actual returns to evaluate the strategy's effectiveness and risk-adjusted performance.  
- **Indicator Analysis**: Contains plots of technical indicators such as:
  - Relative Strength Index (RSI)
  - Moving Averages (MA)
  - Stochastic Oscillator  
- These images demonstrate trends, momentum, and reversal points in the Bitcoin price data, making analysis more intuitive.
![Variable importance](https://github.com/user-attachments/assets/fcfaa824-e790-402e-a0d5-f082c8abcde2)
![Strategy returns](https://github.com/user-attachments/assets/bc4c5213-0495-4035-ab0d-33d431bd7e3a)
![cumulative_returns](https://github.com/user-attachments/assets/7d087771-677f-44fd-8756-518ddd5ff53a)

