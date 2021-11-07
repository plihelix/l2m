# [lightlocalmarket](https://github.com/plihelix/lightlocalmarket) - (L2M) Low Impact Local Market Data Aggregation

## Automates the aggregation of open-source stock market data into a historical database of daily stock price data for analysis.

Currently retrieves ONCE. Full 505 components in the S&P 500 daily history for up to 20 years and stores them in a Mongo-DB. Stored in float-16 for OHLC data and int32 for the volume. Later plans to incorperate an option for more traditional 32-bit floats.

Full daily data approximates 250mb stored.
## *`Notes`
* TODO: Hourly data for about 2.3gb combined.
Full hourly depth is problematic since the logic to validate the data is required. And up next.

# Required MongoDB: [mongodb.com](https://www.mongodb.com/try/download/community)

## *`TARGETS:`*
* collate free stock market data from public sources
* automatically update mongoDB with historical data for the S&P 500

## *`DATA AGGREGATION:`*
    * Request the free API key. Paste it into the config file `.l2m`
    * Copying the config file to your OS specified user home directory is optional but should protect from accidental overwrites.
* [Alpha Vantage](https://www.alphavantage.co/) **`(Working)`**
* [Polygon.io](https://polygon.io/) **`(Working not yet implemented)`**
* [Tradier](https://tradier.com/) **`(Working)`**
* [TBD ...]

## *`Command Line Interface Commands`*
* getindex - imports the current S&P 500 constituents from [Wikipedia](https://en.wikipedia.org/wiki/List_of_S%26P_500_companies)
* run - retrieve daily data for the symbols from Alpha Vantage and Tradier.
* test [SYMBOL] - retrieve the last daily data for the symbol from the database.
* all - list the status of every component in the index

# Setup:

Each API key should be added to the .l2m file in the appropriate location.
The default mongoDb location is local this is currently not required as the URI is also in the .l2m config file. However, no security logic is yet implemented.
