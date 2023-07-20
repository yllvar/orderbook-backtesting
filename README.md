Sure, here is a detailed manual on how to use and understand the backtesting code:

## Backtesting Code Manual

### Overview
The provided backtesting code is designed to simulate trading strategies on cryptocurrency futures data using order book imbalance as the entry signal. The code uses the Kucoin Futures API to fetch historical market data (OHLCV) and Level 3 order book data. It then analyzes the data, simulates trades, and evaluates the performance of the trading strategy.

### Prerequisites
To use the backtesting code, you need to have the following prerequisites:
1. Python 3.x installed on your system.
2. The required Python packages: ccxt, pandas, numpy, matplotlib, seaborn, dotenv, itertools, tabulate, logging.

### Setup
1. Install the required Python packages by running the following command in your terminal:
   ```
   pip install ccxt pandas numpy matplotlib seaborn python-dotenv tabulate
   ```

2. Create a `.env` file in the same directory as the backtesting code. This file will store your Kucoin Futures API credentials. Add the following lines to the `.env` file, replacing `YOUR_API_KEY`, `YOUR_SECRET_KEY`, and `YOUR_PASSPHRASE` with your actual API credentials:
   ```
   API_KEY=YOUR_API_KEY
   SECRET_KEY=YOUR_SECRET_KEY
   PASSPHRASE=YOUR_PASSPHRASE
   ```

### Usage
To use the backtesting code, follow these steps:

1. Import the required libraries and classes:
   ```python
   import os
   import time
   import ccxt
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   import seaborn as sns
   from dotenv import load_dotenv
   from itertools import product
   from tabulate import tabulate
   import logging
   ```

2. Load the API credentials from the `.env` file:
   ```python
   load_dotenv()
   ```

3. Define the `DataFetcher` class, which is responsible for fetching OHLCV and order book data:
   ```python
   class DataFetcher:
       # ... (DataFetcher class implementation)
   ```

4. Define the `OrderBookAnalyzer` class, which contains the backtesting logic and performance metrics calculations:
   ```python
   class OrderBookAnalyzer:
       # ... (OrderBookAnalyzer class implementation)
   ```

5. Define the `optimize_parameters` function, which optimizes the trading strategy parameters using a brute-force approach:
   ```python
   def optimize_parameters(symbol, exchange, limit_entry_params, initial_capital, threshold_positive_range,
                           threshold_negative_range, time_criteria_range):
       # ... (optimize_parameters function implementation)
   ```

6. Define the `setup_logger` function to set up logging for the backtesting process:
   ```python
   def setup_logger():
       # ... (setup_logger function implementation)
   ```

7. Define the `main` function to run the backtesting process:
   ```python
   def main():
       # ... (main function implementation)
   ```

8. Call the `main` function inside an if condition to ensure the script runs when executed directly:
   ```python
   if __name__ == '__main__':
       main()
   ```

9. Initialize the required variables for backtesting, such as API credentials, symbol, timeframe, limit_entry_parameters, initial_capital, threshold ranges, and the logger:
   ```python
   # Define the time duration in seconds for the backtesting loop (e.g., 1 hour)
   backtesting_duration = 3600

   # Initialize the API credentials
   api_key = os.getenv('API_KEY')
   secret_key = os.getenv('SECRET_KEY')
   passphrase = os.getenv('PASSPHRASE')

   # Create an instance of the Kucoin Futures exchange
   exchange = ccxt.kucoinfutures({
       'apiKey': api_key,
       'secret': secret_key,
       'password': passphrase,
       'enableRateLimit': True  # Adjust as needed
   })

   # Initialize the symbol, timeframe, and limit_entry_parameters
   symbol = 'ETH/USDT:USDT'
   timeframe = '5m'
   limit_entry_parameters = {'ETH/USDT:USDT': {'limit': 1000}}

   # Define the initial capital for the backtesting
   initial_capital = 100

   # Define the threshold ranges for the trading strategy
   threshold_positive_range = [40, 50, 60]
   threshold_negative_range = [-80, -75, -70]
   time_criteria_range = [4, 5, 6]

   # Initialize the logger
   logger = setup_logger()

   # Initialize the 'data_fetcher' variable
   data_fetcher = DataFetcher(exchange, symbol)
   ```

10. Perform the backtesting logic inside a loop for the specified duration:
   ```python
   # Get the end time for the backtesting loop
   start_time = time.time()
   end_time = start_time + backtesting_duration

   # Initialize the 'symbol' variable outside the loop
   symbol = 'ETH/USDT:USDT'

   while time.time() < end_time:
       # ... (backtesting logic inside the loop)
   ```

11. Use the `OrderBookAnalyzer` class to run the
