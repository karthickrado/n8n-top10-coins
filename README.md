## Top 10 Coins Workflow

**Overview**
This workflow pulls live market data from CoinGecko for the top 10 cryptocurrencies by market cap, transforms and rounds the data, adds a timestamp, and exports it to an XLSX file (can be adjusted). It can run on a schedule (currently hourly).

**Setup**
1. Create a free CoinGecko account and generate an API key (the workflow should run without a key, but having a key ensures more reliable, stable data).
2. Add your API key in the HTTP Request (CoinGecko API) node under 'Header Parameters':

Name: 'x-cg-demo-api-key'
Value: **your API key**

3. (Optional) Adjust the API URL in the HTTP Request (CoinGecko API) node to change: 

 **Currency**: 'currency=gbp' (or 'usd')
 **Number of Coins**: 'per_page=10' (or '100')

## Filtering & Rounding

**Filters**
- Only the following fields are included and renamed for readability: Name, Symbol, Price (GBP), Market Cap (GBP), Price Change (%).
- Fields can be adjusted depending on your use case.


**Rounding**
- Price and Price Change are rounded to 2 decimal places.
- Market Cap is rounded to the nearest GBP billion to improve readability.


**Note**
The 'Retrieved' column timestamps the data for better future comparability. 
