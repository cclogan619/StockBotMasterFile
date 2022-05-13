# StockBotMasterFile
Project_1_Group_1_Visualization

The Master File for the StockBot Group Project uploaded to my GitHub
This is the repository of  work for Project 1

https://files.slack.com/files-pri/T034H24LSKZ-F03ED78RXJ8/flow_chart.drawio.png
END PRODUCT 

- EMAIL/TEXT 
	- table of current prices and changes from last update
	- Recommendation about trajectories
		- SMA/LMA display over graph
		- Graphs for other tickers maybe
	- Graph of past N days
	- Graph of trajectory (Lin Reg etc)


table of current prices and changes from last update - aaron
	- data of last update
	- data of current prices
	
Recommendation about trajectories - todd
	- daily closes for past N months
	- Calculate SMA/LMA from aformentioned data
	- graph SMA/LMA over daily closes
	
Graph of past N days - catherine
	- daily closes and percent changes for past N days

Graph of trajectory (Lin Reg etc) - Later
	- daily closes of past N months 
	- MA of daily closes
	- Lin Reg for MA


Block 1: Jaime's code - pulling data from data sources and putting them into CSV files. Block 2: Todd's code - Taking those CSV's and massaging the dataframes so that they do the following: a. Only have the number of data points in the requested time interval b. removing all but the closing data, leaving the timestamp and "Closing" prices c. plotting that data in a simple line graph Block 3: Visualizations

Additional modifications to Block 2 and merging the code in Block 1

Here's the current state of the project from what I'm calling "Block 2." My code pulls the CSV files provided by Jaime "Block 1" and puts it into a usable format to build a simple moving average (SMA). This was uploaded on May 7, 2022 (after our TA session - Saturday) at 2:43 p.m. central time.

From this point, I will work toward creating functions that do the heavy lifting so they can be called by one main program.
I will push up that code block to this repository after that's done. Second activity will be to merge Jaime's code with my code.

Once I get a working code from Todd or Aaron. I can find out what graphs they wish to present their work.

We all decided have a three overlaid line graph of the result for each category: S & P 500, NASDAQ, BTC, ETH

Sample of Code I found that can help achieve the overlaid Three line graph
but it needs help to achieve this 
import matplotlib.pyplot as plt
plt.style.use('classic')
%matplotlib inline
import numpy as np
import pandas as pd

rng = np.random.RandomState(0)
x = np.linspace(0, 10, 500)
y = np.cumsum(rng.randn(500, 6), 0)

plt.plot(x, y)
plt.legend('ABCDEF', ncol=2, loc='upper left');
![image](https://user-images.githubusercontent.com/101228807/168193112-66c2e2a4-9ad7-4839-81a8-53719da5e0f0.png)

Todd or Aaron made this code for the project I was stuck 
sp500_new_df.hvplot()
nasdaq_new_df.hvplot()
btc_new_df.hvplot()
eth_new_df.hvplot()
###SMA-cell
btc_new_df['10_Day_Rolling'] = btc_new_df['Close'].rolling(window = 10).mean()
btc_new_df['20_Day_Rolling'] = btc_new_df['Close'].rolling(window = 20).mean()
btc_plot = btc_new_df.hvplot()
btc_plot
hv.save(btc_plot, filename = 'btc_ma.png')
###SMA-cell
eth_new_df['10_Day_Rolling'] = eth_new_df['Close'].rolling(window = 10).mean()
eth_new_df['20_Day_Rolling'] = eth_new_df['Close'].rolling(window = 20).mean()
eth_plot = eth_new_df.hvplot()
eth_plot
hv.save(btc_plot, filename = 'eth_ma.png')
###SMA-cell
sp500_new_df['10_day_Rolling'] = sp500_new_df['Close'].rolling(window = 10).mean()
sp500_new_df['20_day_Rolling'] = sp500_new_df['Close'].rolling(window = 20).mean()
sp500_plot = sp500_new_df.hvplot()
sp500_plot
hv.save(sp500_plot, filename = 'sp500_ma.png')
###SMA-cell
nasdaq_new_df['10_Day_Rolling'] = nasdaq_new_df['Close'].rolling(window = 10).mean()
nasdaq_new_df['20_Day_Rolling'] = nasdaq_new_df['Close'].rolling(window = 20).mean()
nasdaq_plot = nasdaq_new_df.hvplot()
nasdaq_plot
hv.save(nasdaq_plot, filename = 'nasdaq_ma.png')


The presentation is May 12,2022 during classhours. 

I made a Power Point presentation and I needed the graphs to apply to the presentation. 
THis did not happen. 


© 2022 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
