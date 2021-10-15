# Portfoilio-allocation-and-automatic-rebalancing-Stocks-T-Bonds
The scope of this assignment is on asset allocation, or the allocation of portfolios to basic building blocks such as stocks, government bonds, Treasury Bills, and other asset classes such as real estate and corporate bonds.  
The scope of this assignment is on asset allocation, or the allocation of portfolios to basic building blocks such as stocks, government bonds, Treasury Bills, and other asset classes such as real estate and corporate bonds.  

1.	Data Definition 

The data file contains annual returns for the S&P 500, T-bill, US T.bond, Baa  corporate bonds. The data collected is from 1928 -2020 annual period returns. The data file was last updated on 01-Jan-21. We are using the time from 1928-2020 for our analysis. As using the longest data period, we would allow us to derive insights as to people’s preference for risk has evolved overtime. Furthermore, we want to understand what drives their decision to buy a risky asset vs a non-risky asset. All this data helps us comprehend how the market reacted when there were moments of inflation, which we are currently facing. 

The data file was located and downloaded on 17-June -2021from the following link:-
http://www.stern.nyu.edu/~adamodar/pc/datasets/indname.xls

1.	Stocks - The data of S&P 500 stocks are considered for the analysis. The dividend yield is calculated by dividing the dividends paid by the index at the end of the prior year and then adding the price change in the index, as a percent of the index in the prior year.

2.	US Treasury bond- The 10-year US treasury bond returns are taken into consideration. The yields here used are on a constant - maturity 10-year bond taken from the FRED (federal reserve website). The yield is converted into a return, by repricing the bond, issued at par at the prior year's yield, with the new yield, while keeping the maturity constant at 10 years.

3.	US T.Bill- The data contains a 3-month US treasury bill, choosing it over the 6-month because of longevity. The T.Bill rate at the end of each year from FRED and are used as return, since there would be no price change in this security.

4.	Aaa & Baa Corporate Bond-  The data is from the Moody's Aaa and Baa corporate bond yields from FRED and then return is computed on the bond, using the above approach that was used for the US T.Bond.

Visualization & Analysis 

The table below is a summary of statistics for excess returns of the assets in the portfolio. The excess returns were calculated by using the dataset. From the summary statistics we can make the following observation.

Mean- The average return helps us in understanding the returns over the past performance of the assets. From the data we can see that the mean returns of the Stocks(0.082) was highest and that of the treasury bonds(0.0185) was the lowest. With Corporate bonds (0.0389) having the returns between Stocks and T- bonds returns. 

Stocks have historically delivered higher returns (0.082800) as compared to bonds because stocks factor in risk, which can lead to higher rewards due to the variability. If the company fails, all of the stockholders' investment will be lost. However, a stock's price will also rise in spite of this risk when the company performs well and can even work in favor to the investor.

T-bonds have lower yield (0.018514) as can be seen in the table as they are risk free. They are added to assets because High-quality bonds like U.S. Treasuries offer diversification benefits when added to a portfolio of stocks. Treasuries tend to be more defensive in nature, and their returns tend to have a negative correlation with stock market returns.

Corporate bonds have higher risk than the T.bonds, but it gives more returns in the longer term as compared to the T.bonds.

Sharpe ratio -  Sharpe ratio is a measure of excess portfolio return over the risk-free rate relative to its standard deviation. In a way it's providing a measure to understand by combining the mean and standard deviation. 

The sharpe ratio for corp bonds(0.517250) is high as compared to the T-bond(0.241804) which is lowest , with stocks((0.424874)) among the three assets. 

The overall sharpe ratio is very low for all three assets, any Sharpe ratio greater than 1.0 is considered acceptable to good by investors. A ratio higher than 2.0 is rated as very good. A ratio of 3.0 or higher is considered excellent.

Standard deviation-  As from the table we can see that Stocks have the highest deviation of (0.1982), which means the stocks have the highest volatility and hence highest risk as compared to the other assets. The stddev of the corporate bonds(0.07862) is close to the T.bond(0.0745) which is very intriguing. Generally, the corporate bonds have higher risk as compared to T.Bonds ,which are backed by the government. 

Kurtosis-  Kurtosis is the fourth standardized moment. From the table we can see that kurtosis for all three assets is near zero which is less than normal distribution at 3 , which means its platykurtic kurtosis, which means a platykurtic distribution will have thinner tails than a normal distribution will, resulting in fewer extreme positive or negative events. It means in longer term all three assets were good for investors who minimize the risk of large negative events, risk-averse investors could have focused in these platykurtic assets


 
Table 1 a: Summary statistics for excess returns of assets in the portfolio
Correlation 
Correlation represents the degree of relationship between the price movements of different assets included in the portfolio. A correlation of +1.0 means that prices move in tandem; a correlation of -1.0 means that prices move in opposite directions. A correlation of 0 means that the price movements of assets are uncorrelated; in other words, the price movement of one asset has no effect on the price movement of the other asset.
From the table 1b we can see that the stocks have more correlation with corporate bonds (0.4415)as compared to Stocks’s correlation to the T.bonds(0.022916). It shows that there might be some similar factors affecting the returns for both Stocks and Corporate bonds. 
Corporate bonds have correlation of 0.6005 with T.bonds, suggesting some higher factors affecting the corporate bonds and t.bonds, even though the T.bonds are risk free and the Corporate bonds are risky.




Table 1 b:
2.Methodology 
We were asked to calculate the risky asset allocation for the minimum variance portfolio and the portfolio sharpe ratio. To get those results we create a function to give us the different weights. We extracted the stocks, t bond and corporation bonds columns. Then we created a variable to carry the weights for each respective asset that would be equal to 1. Since we knew this was an optimization problem we added a constraint where we subtracted the sum of the weights from 1. We also added bounds so that the values are within 0 to 1. Finally, we created the variable res which is the variable the will  print all the results from the simulation. We used the function scipy optimization (figure 1A) to give us the minimum variance, which is denoted in the first line of the output of the res variable. The simulation runs for about 5 times and it prints the optimal weights in the last line of  the res variable.
Figure 1a
The best returns with the minimum variance are 0.036 for stocks, 0.529 for t bonds and 0.434 for corporate bonds. The investor should not take any returns that are less than these.
For the Sharpe ratio, we also create a function that takes the formula, which is the ratio of the mean and standard deviation respectively. The function contains weight that are all equal to 1. However, note that these are not the optimal weights the function scipy optimize will be responsible to find them. Again, our bounds for the weights are within 0 to 1.  The optimization simulations runs for 7 times and it is able to give us the weights for stocks, t bonds and corporate bonds. See more information in the code file.
3. Results and Interpretation:
B.1- The minimum variance portfolio (MVP) indicates a well-diversified portfolio that consists of individually risky assets, which are hedged when traded together, resulting in the lowest possible risk for the rate of expected return. 
 Portfolio weights to achieve minimum variance portfolio                    Minimum standard deviation.    
 W1
 (stocks)	w2 
(T.bonds)	W3 
(Corp.bonds)
0.0362	0.52959	0.4341
0.06801



 B.2- MSRP- Maximum Sharpe Portfolio or Tangency Portfolio is a portfolio on the efficient frontier at the point where the line drawn from the point (0, risk-free rate) is tangent to the efficient frontier. 
Portfolio weights achieve MSRP
W1	
(stocks)	w2
(T.bonds)	W3 
(Corp.bonds)
0.203806	0.04116	0.7550
B.3- Asset allocation and summary statistics for MVP and MSRP for three risky asset cases.
	MVP	MSRP
MEAN	0.0297	0.0470
STDEV	0.0680	0.0866
SKEW	-0.0119	-0.4877
KURT	0.0360	0.2263
AUTOCORR	0.088796	0.1071
SHARPE RATIO	0.4366	0.5426
Table 2 a
B.4- Figure that traces out the efficient frontier using only the three risky asset excess returns. Also, MVP and MSRP. The same axes show what happens to the efficient frontier if you add a riskless asset.  
Fig – 1 b
Interpretation
•	The table 2a shows the moments for the asset 3 risky asset cases. From the table we can see that the mean return for the MSRP is higher than the MVP, suggesting a better approach to gain returns with balanced risk. Investments with a higher Sharpe Ratio are preferred because we are assuming less risk for reward. Portfolios that offer the same returns with more risk or less return for the same risk are inefficient and are not found on the efficient frontier.
The stdev of the MSRP is higher than the MVP, but it balances due to higher returns form the MSRP portfolio. The SHARPE ratio of MSRP is better as compared to the MVP, which means MSRP portfolio are better suited with better returns. 
•	The figure 1b shows the plot of the that traces out the efficient frontier using only the three risky asset excess returns. Also, MVP and MSRP. The same axes show what happens to the efficient frontier if you add a riskless asset.
•	The table 1b shows that the Kurtosis of the MSRP was higher than the MVP, which means MVP has more weight in the right tail and hence relatively lower risk of extreme values.
•	For MVP, more weight was in T.bonds(53 %), the second highest was in the corp bonds (43%), with least being in the stocks (4%). While in MSRP, largest was in Corp bonds with approx 76%, second highest was in stocks -20% and the least was in the T.bonds (4%). Since Corp Bonds have lower standard deviation and also decent return(see Table 2a), its aligns with the having highest portfolio allocation.
•	 We can see that by adding riskless assets, the efficient frontier does not change much and remains and almost similar. Which could mean the portfolio is highly efficient and returns are high enough for given standard deviation. Also, the riskless asset added has similar stdev and mean and hence not much impact.
•	 The MVP point is lower than MSRP point in Figure 1b. As already seen from the table 1, the returns for the MSRP portfolio are higher as compared to the MVP. 
C.1- Additional results for  MVP and MSRP in  two risky asset cases with 3 risky case and their moments
	MVP	MSRP	MVP 2 assets	MSRP 2 Assets
MEAN	0.0297	0.0470	0.0261	0.04377
STDEV	0.0680	0.0866	0.0703	0.0910
SKEW	-0.0119	-0.4877	0.1992	-0.2462
KURT	0.0360	0.2263	0.0338	-0.1300
AUTOCORR	0.088796	0.1071	-0.0690	0.0300
SHARPE RATIO	0.4366	0.5426	0.3713	0.6224
Table 2b
C.3-  Figure that shows how the efficient frontier changes going from the three-risky-asset to the two-risky-asset case.
Fig- 2
Interpretation 
•	As can be seen from the Table 2b adding diversification i.e., adding the assets with lower co-relation would increase the Sharpe ratio compared to similar portfolios with a lower level of diversification and hence it would help in better returns. 
•	Yes, by adding a risky asset to 2 risky asset portfolios, it does change the result as can be seen from the plot. This could be due to the diversification of portfolio with more assets which are not corelated to leads to more efficient portfolio. As above it can be seen that the with addition of risky assets, the mean return increased for 3 assets portfolio with similar level of risk of 2 risky asset portfolio.
•	From the table 2a, we can see that the Kurtosis of the MSRP 2 assets was lowest and the MSRP of 3 assets risky was the highest, suggesting the 2 asset MSRP would be at lower risk of getting extreme returns. 
•	We can see that from the above plot that MSRP of 3 risky assets was higher as compared to the 2 assets MSRP and 3 assets MVP. It means that by adding a risky asset to a 2 risky asset portfolio, it helps in getting better return at similar level of standard deviation. 
•	From the table we can see that the kurtosis of the assets are less than 3 , the normal distribution and hence are platykurtic distribution. Which means that even after the addition of risky assets the Kurtosis did not change much for the portfolio. We would not expect any extreme returns either positive or the negative.
•	We can see from the Table 2b, the auto co-relation of portfolio increased after addition of the risky asset to the portfolio. But the increase was not much and hence the resulting portfolio was diversified enough
