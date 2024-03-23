 Project Title: SENTIMENT ANALYSIS AND PRICE PREDICTION OF TOP CRYPTOCURRENCIES
 
## Project Description
In this project description, we will cover:
* Project Overview
* Business Problem
* Business Understanding: 
  - Explaining stakeholders
  - Business questions
* Data Analysis:
  - Source of data and deliverables
  - Data Understanding
* Conclusion:
  - Key findings 
  - Recommendations
  - Summary and next steps

## Project Overview
The project "Sentiment Analysis and Price Prediction of Top Cryptocurrencies" aims to leverage sentiment analysis to predict the price movement of three major cryptocurrencies: Bitcoin, Ethereum and Ripple. With the increasing interest in cryptocurrency investments, understanding market sentiment has become crucial for making informed decisions. However, integrating sentiment analysis with price prediction poses significant challenges due to the volatile nature of cryptocurrency markets.

- Main objective: Improve investment decision-making and optimize returns
- Approach: Utilize data-driven insights and predictive analytics
- Target audience: Traders, investors and analysts
- Purpose: Assist in making well-informed choices regarding cryptocurrency investments and trading strategies

## Business Problem
Cryptocurrency markets are highly volatile and influenced by various factors, including market sentiment. Traders and investors often seek ways to leverage sentiment analysis to make informed decisions about their investments. However, integrating sentiment analysis with price prediction for cryptocurrencies remains a challenging task. This project aims to address this challenge by conducting sentiment analysis on three top cryptocurrencies, namely Bitcoin, Ethereum, and Ripple, and subsequently using the sentiment analysis results to predict the price movement of the most positively sentimented cryptocurrency over the next 30 days.

## Business Understanding

* Target Stakeholders: 
- Cryptocurrency Traders: Actively buy and sell cryptocurrencies for profit.
- Cryptocurrency Investors: Entities who invest in cryptocurrencies for long-term growth and potential returns.
- Financial Analysts: Professionals who analyze financial data, including cryptocurrency market trends, to provide insights and recommendations.

#### Business questions.

1. What are the sentiments expressed in online discussions, news articles, and social media platforms regarding Bitcoin, Ethereum, and Ripple?
2. Which cryptocurrency exhibits the highest positive sentiment among Bitcoin, Ethereum, and Ripple?
3. How can sentiment analysis be effectively integrated with price prediction models for cryptocurrencies?
4. What factors contribute to the accuracy and reliability of sentiment-based price predictions for cryptocurrencies?

## Data Analysis
#### The Source of Data

* This project fetches news articles about Bitcoin, Ethereum and Ripple using the News API. For each cryptocurrency, we retrieve the titles and descriptions of the top news articles based on relevance.
* We will retrieve historical price data for Ethereum from Yahoo Finance using yfinance python library. This data will include historical open, high, low, close prices, as well as trading volume and other relevant metrics.
* We have already done the retrievals of the data using APIs and you could assess our progress using the collab link below
https://colab.research.google.com/drive/19xCmNV1HqlQinpW5uGJNbwP4PV2474-1?usp=sharing

#### Deliverables
There are three deliverables for this project:

1. A **non-technical presentation** - 
2. A **Jupyter Notebook** - 
3. A **GitHub repository** - https://github.com/otienobaker1/SENTIMENT-ANALYSIS-AND-PRICE-PREDICTION-OF-TOP-CRYPTOCURRENCIES

#### Data understanding 
- We begin by installing Python packages using pip (Package manager for python): 
> %pip install newsapi-python: Installs the newsapi-python package for accessing news articles through the News API.
> %pip install serpapi: Installs the serpapi package for fetching search engine results programmatically.
> %pip install yfinance: Installs the yfinance package for retrieving financial data from Yahoo Finance.
> %pip install yahooquery: Installs the yahooquery package for querying financial data from Yahoo Finance.
> %pip install nltk: Installs the nltk package for natural language processing tasks.
> %pip install autots: Installs the autots package for automated time series forecasting.

**IMPORTING LIBRARIES AND DATA ANALYSIS**
- We then import the necessary libraries:
> NewsApiClient from newsapi, nltk and matplotlib.pyplot.
- Initialize the News API client using the provided API key.
- Define a function `fetch_articles(query)` to fetch news articles for a given query.
- The function:
> Retrieves news articles based on the provided query using the News API client
> Formats the title and description of each article into a single string and appends them to a list of formatted articles
> Returns the list of formatted articles.

- The lines of code that come after define two functions:
> The function analyze_sentiment(text) to analyze the sentiment of a given text by categorizing it as positive, negative or neutral based on the sentiment score obtained from the SentimentIntensityAnalyzer.
> plot_sentiment_distribution(sentiment_counts, title) to plot the distribution of sentiment.

- News articles are fetched for Bitcoin, Ethereum and Ripple. Then, sentiment analysis is performed on each set of articles and the counts of positive, negative, and neutral sentiments are calculated for each cryptocurrency.
- Finally, the sentiment distribution for each currency is plotted. 
![Bitcoin_Sentiment_distr](Bitcoin.png)
![Ethereum_Sentiment_distr](Ethereum.png)
![Ripple_Sentiment_distr](Ripple.png)

- Now, to fetch historical price data we import: 
> The pandas library for data manipulation and analysis, while yfinance serves as a Python client for accessing Yahoo Finance's API.
> The datetime module for date and time manipulations making it easier for the retrieval and processing of historical cryptocurrency price data.

- The current date is obtained and is formated as d1 for the end date. Calculates a date 768 days prior to the current date and format it as d2 for the start date. 

- Downloading Historical Data for the Ethereum cryptocurrency ('ETH-USD') using the yfinance library, specifying the start and end dates for the data retrieval.
- Data Preprocessing:
> Adds a 'Date' column based on the index of the DataFrame.
> Reorders the columns to a specific sequence ('Date', 'Open', 'High', 'Low', 'Close', 'Adj Close', 'Volume').
> Reset index and drop the existing index column.

- Visualizing Data:
> Import the `plotly.graph_objects` library to create a Candlestick chart using Plotly, representing the open, high, low and close prices of Ethereum over time.
> The layout of the chart sets the title and hiding the range slider on the x-axis.
![Ethereum_Price_Analysis](EthereumGRAPH.jpg)

- Calculating Correlation:
> The correlation matrix is calculated specifically focusing on the correlation of the 'Close' price with other variables.
> It is seen that 'Close' has a perfect positive correlation with 'Adj Close', 'High', 'Low' and 'Open' since they have correlation coefficients close to 1.
> The 'Volume' variable has a low positive correlation with 'Close', showing a weak positive relationship between the closing price and trading volume.

- Importing AutoTS:
> A Python library for automated time series forecasting.
> Initialize an AutoTS model with parameters specifying the forecast length (30 days), frequency (automatically inferred), and ensemble method (simple averaging).
> The model is then trained on the provided data, specifying the date column ("Date"), value column ("Close") and no identifier column.
> Once the model is trained, predictions are generated using the predict() method.
> The forecasted values are extracted from the prediction object and stored in the forecast variable.
> The output shows details of the model's training progress, including the model number, type of model, generation number and loss values for each epoch during training.

## Conclusion 
Based on the analysis conducted, our model has provided a forecast indicating that as of April 16, 2024, the price of Ethereum cryptocurrency is predicted to be approximately USD 3254.133361. However, it is important to recognize that cryptocurrency markets are highly volatile and subject to various external factors that can significantly influence price movements. Therefore, while this forecast provides valuable insight, it should not be viewed as a definitive outcome.

#### Key Findings

1. Sentiment affect crypto markets and can potentially shape investor decisions and market trends.
2. Showed the ability to predict crypto prices using historical data, emphasizing automated forecasting's effectiveness.
3. Visual insights offered Ethereum's price behavior, revealing trends, volatility and potential patterns.

#### Recommendations

1. Approach investment decisions with caution and understand inherent risks
2. Consider diversifying portfolios to mitigate potential losses
3. Explore alternative investment strategies aligned with risk tolerance and financial objectives
4. Stay informed about cryptocurrency industry developments
5. Monitor regulatory changes, technological advancements, and market trends
6. Engage with reputable sources of information and seek advice from financial experts
7. Regularly review and adjust investment strategies based on changing market conditions and financial goals
8. Adopt a proactive approach and remain vigilant to capitalize on opportunities and minimize risks in the cryptocurrency ecosystem

#### Summary and next steps
- Ethereum exhibits the most positive sentiment among the three, therefore:
1.Retrieve historical price data for Ethereum using yfinance.
2.Predict Ethereum's price for the next 30 days using machine learning.
3.Train a model incorporating historical price data, sentiment scores, and other features.
4.Evaluate model performance and make informed investment decisions.
