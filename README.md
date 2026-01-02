# Sentiment_Analysis

# Problem Statement: 

This project analyzes how trader performance changes under different market emotions such as fear and greed. The goal is to understand when traders perform best and how emotions influence trading decisions. 

# Dataset:

## Market Data:

- The market has moods - fear or greed. fear meaning the prices are expected to go down, and greed, the prices go up.

- These moods are measured at different timestamps starting from a particular date.

- Rows: 2644

## Trader data:

a) start position - initial value present in the account before this trade. 

b) directions, 

- Open: the trader enters a trade by buying.

- Close: the trader exits the trade by selling.

- Long: the trader expects prices to go up.

-Short: the trader expects prices to go down.

c) closed PnL: net profit after the trade.

d) crossed: true if it’s executed immediately at the current market price (aggressive).

- Rows: 211224

# Tools:

Pandas

Numpy 

Matplotlib

Seaborn 

# Approach and Methodology:

## Data Cleaning:

- Checked for null/ missing values and duplicates (none).

## Data Preprocessing and Integration:

- Converted the columns in both market and trade data to date-only (easy to merge). 

- Dropped unnecessary columns that do not affect the data analysis, like ‘Transaction Hash', 'Order ID', 'Trade ID’.

Converted the columns ‘crossed’ and ‘sell’ to numerical ones. 

Merged the two datasets based on their dates. However some trades did NOT have a matching market sentiment so they were eliminated. 

# Feature Engineering:

Created a new variable pnl_ratio (closed pnl / size) to measure How much profit (or loss) did the trader make per dollar risked?

# Data Visualization: 

## Profits across sentiments: 

- The net profits were observed for each sentiment and clearly there was more profit when greed.

- Greed often means prices are rising, so traders find more chances to make money.

- The boxplot for the same shows that the variations have greed phases with wider swings and more chances for higher profits.

- Similarly win rate was measured, (only profits) and it was highest for extreme greed and greed and least for neutral.

## Direction vs Sentiments:

When the no of trades were plotted for each direction type (only open and close long and short), it is seen that during fear, traders are most active, frequently adjusting both long and short positions.

## Risk Behavior:

- Overall Size USD was plotted at different sentiments, it’s clear that extreme emotions lead traders to place bigger trades, showing higher risk appetite during fear and extreme greed.

- Crossed rate was plotted against sentiments to see that neutral markets saw the most aggressive trading, with more trades executed immediately at market price.

- However, the efficient trades happened during greed (pnl_ratio).

# Conclusion:

- When traders panic or get overly excited, they trade more and risk more money, but that doesn’t always help them earn better.

- Fear makes people react quickly, and extreme greed makes them overconfident.

- In short, calm confidence works better than emotional trading.

# How to run the project:

- Download or clone the repository.

- Open the project folder.

- Open the Jupyter Notebook file (.ipynb).

- Run all the cells from top to bottom.

# Project Structure: 

├── fear_greed_index.csv , historical_data.csv      # Dataset used in the project

├── trade.ipynb      # Jupyter Notebook with full code

├── README.md          # Project explanation
