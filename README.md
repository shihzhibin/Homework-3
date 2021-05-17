# Homework-3
You will act as a house owner in this HW3
Your house equipped with appliances and solar power plant
Your house is in a community microgrid with a total 40 households 
You can decide to buy or sell the power from the microgrid through a local power trading platform
You can still consume the power from the main grid by a fixed price 
Goal: Design an agent for bidding power to minimize your electricity bill

Data
50 households synthetic data
Hourly Power consumption (kWh)
Hourly Solar Power generation (kWh)
Hourly Bidding records
12 months of data
8 months for training
1 months for validation
3 months for testing


Workflow 
1.Platform inputs the past 7 days of consumption data(consumption.csv), generation data(generation.csv) and bidding records(bidresult.csv) to every agent
2.Agent generates the following day of hourly bidding action(output.csv) and outputs to the specific path
3.Platform crawls the bidding action of all agents and proceeds a bidding match
4.Platform announces the bidding result(bidresult.csv) and outputs it as a file to every agent’s directory

Action type
Buy
Find a seller to buy your power with target_volume and target_price
If a transaction succeeds(成交), buyers always get the trade_volume with trade_price
Sell
Find a buyer to buy your power with target_volume and target_price
If a seller sells the amount that insufficiently supply to a buyer, seller needs to buy the power from Taipower and supplies it to buyer with the market price (市電單價), annotated as market_price.
No Action
Don’t output any bidding action to output.csv in these hours 


Bidding rules
Hourly bidding action(output.csv) should comply with the following specification:
An agent can sell or buy in the same hour, and the maximum number of taking actions is 100 a day
Bidding action should be in hour interval, format: %Y-%m-%d %H:%M:%S
Bidding price and bidding volume will be rounded to 2 decimal places







