# Volatility-Prediction
The primary aim of this project is to perform volatility prediction for use in a pairs trading strategy. Divided into three main sections—Asset Selection, Volatility Prediction, and Pair Trading—the project employs a comprehensive approach that combines fundamental analysis, statistical modeling, and machine learning techniques. Through these methods, the project seeks to offer valuable insights to investors aiming to optimize their trading strategies and improve portfolio performance.
### Code and Resources Used:<br>
**Jupiter Notebook**<br>
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, pmdarima, scipy, statsmodels <br>
**Financial Metrics:** Greenblatt's Screener, Piotroski Score, Beneish M Score,  Altman Z score, Sharpe ratio, Annualized Percentage Rate<br>
**Statistical Testing:**: White Reality Check
### Data Collection & Cleaning:<br>
##### Asset Selection:<br> 
The foundation of any trading strategy lies in the careful selection of assets with strong fundamentals and growth potential. To achieve this, a combination of screening tools and financial scoring systems is utilized. Initially, Greenblatt’s screener is employed to identify 50 stocks with a minimum Market Cap of $50 million. These stocks are then further filtered using robust scoring systems such as Piotroski for growth potential, Altman for bankruptcy risk evaluation, and Beneish for detecting potential accounting fraud. Subsequent analysis involves calculating the annual percentage return and volatility for each stock. Clustering techniques, specifically K-means clustering with k = 6, reveal cluster 1 as an optimal choice, comprising assets with the lowest volatility and strong fundamental scores, including MED, MLI, and MPX.<br>

![image](https://github.com/user-attachments/assets/79042f9a-1674-4fa1-82a5-327342faeb85)


![image](https://github.com/user-attachments/assets/31d95d9f-f5b4-4228-acc8-38c620c7182c)


![image](https://github.com/user-attachments/assets/5a32c890-b79d-4370-817b-667af11f3879)

### Model Building:<br>
##### Volatility Prediction<br>
In this section, the close prices of the selected assets are utilized to predict volatility using various models including **ARCH**, **GARCH**, **SVR-GARCH**, and **Neural Network** models. The performance of these models is compared using the Root Mean Square Error (RMSE), as shown in the table below:<br>
![image](https://github.com/user-attachments/assets/41a25a48-ae6a-49da-9051-2419d4e72ceb)


The results indicate that the SVR-GARCH model outperforms the other models regarding volatility prediction.<br>
#### Pairs Trading:
Before implementing the trading strategy, a cointegration test is conducted on the selected stocks to assess their suitability for pairs trading. The Johansen test is utilized for cointegration testing, providing insights into the long-term relationship between asset prices and hedge ratios for portfolio allocation. The SVR-GARCH model is then used to predict portfolio volatility and define trading signals. Performance metrics such as the Annualized Percentage Rate (APR) and Sharpe Ratio are calculated to evaluate the trading strategy, with a Sharpe Ratio of 1.65 indicating profitability. A White Reality Check is performed, yielding a p-value of 0.007, allowing us to reject the null hypothesis and affirm the observed profitability.
![image](https://github.com/user-attachments/assets/0169515b-e24f-4ef4-9408-8f698132043a)

![image](https://github.com/user-attachments/assets/4cda654b-7d40-4d43-8d10-620cfb65b574)

#### Conclusion
In conclusion, this project provides a comprehensive framework for volatility prediction and pairs trading strategies. By comparing traditional time series models with machine learning models, it demonstrates the superior performance of ML models. Furthermore, the pairs trading strategy, informed by these predictive models, showcases promising profitability and risk management results.


