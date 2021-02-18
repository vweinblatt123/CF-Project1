# The Reddit Trade
## An analysis of social media’s impact on stock performance

Weirong Tian, Yuttakarn Limleartvate, Siegfried Vieluf, Victor Weinblatt

(Please see our main deliverable ![here](CF-Project1.pptx), and browse the various folders to see accompanying notebooks, graphs, and data, not highlighted below)

*Fundamental setup: weak metrics for GME, a brick and mortar video game company during a global pandemic*

Gamestop is a retailer, selling video games, consumer electronics and merchandise related to video games in the United States, Canada, & Europe. As a brick and mortar video game retailer in the middle of a global pandemic, the company understandably displays weak fundamentals. We analyze these ![here](Ziggy/fundamental_story.ipynb). We analyzed fundamentals from four perspectives: growth, profitability margins, debt ratios, and market capitalization versus enterprise value. From a growth perspective, revenue is expected to go down 22%, earnings per shares is expected to go down 90%, and EBITDA is expected to go down by 56%. Amongst their competitors GameStop is the worst performer. It appears GameStop is losing sale opportunities while maintaining all its cost, likely due to real-estate related expenses. Then, from a margins perspective, GME is expecting and have received low bottom line margins compared to its peers. GameStop has a 4.4 EBITDA margin, a -3.5 Operating Income Margin, and a -3.15 Profit Margin. From a debt perspective, GameStop is not necessarily the worst but for a mature company, and given  its size, having a debt/ebitda ratio of 5 is high amongst its peers. GME's interest ratio is reflective of the accomodating years we have seen of late, with low interest rates. What is interesting is the price to free cash flow ratio, which at 22x free cash flow is astronomically high for the industry, and with such low expectations in revenue, operating margin, and net income, is unrealistic. Finally, we analyze GME's market capitalization versus enterprise value. Most companies have lower enterprise values than market cap, because the latter subtracts cash from total debt. However, GME does not have sufficient cash so their enterprise value is higher than their market cap. This is important because throughout this Reddit chapter of their lives they did not sell equity when the stock price was elevated (and cost of capital cheap), building a financial warchest for the future. Fundamentally, speaking GameStop has negative expectations and weak fundamentals. 

*Technical setup: hedge funds had accumulated a very large short position*

As a result of the weak fundamentals, hedge funds established a large short position (more than 100% of the float) to bet against the name. The short really accelerated at the end of last year, into January. We pull historical Bloomberg data to create a "short trend" graph ![here](weirong/GME_short.ipynb).

*Sentiment analysis: daily movements in stock prices impacted by WSB posts*

Wanting to "stick it to the man" and "fight the hedge funds", retail investors began buying up GME shares at very cheap prices. A notable forum for discussing stocks amongst these investors is the Reddit wallstreetbets (WSB) page. We pull posts from this forum over the second half of January until early February to analyze how sentiment in the forum has driven stock price performance amongst most talked about names (not just GME, but also AMC, BBBY, NOK, and BB). We create a "wordcloud" highlighting popularity of particular words in titles of WSB posts and compare daily price movements in an equal weighted portfolio of these "Reddit stocks" to daily sentiment from the forum. We use Kaggle data, along with the praw Reddit api, and the nltk NLP package to analyze sentiment ![here](Victor/reddit_processing.ipynb) and ![here](Victor/reddit_analysis.ipynb).

*Returns, Betas, and Sharpes*

The resulting stock movements in these names created some very interesting statistical results. We look at rolling 120-day betas as well as Sharpe ratios of these Reddit names vs the S&P 500, individually and as an equally weighted portfolio ![here](Yuttakarn/Risk.ipynb). We see betas get to extremes of -5; on days these names did particularly well, the market overall was selling off as fear of bubbles, extended leverage, and regulatory repercussions saw the rest of the market underperform (and vis-a-versa). Of note, Sharpes using one year of data were consistently greater in these Reddit names than the overall market, and just looking at the last month of data, GME's Sharpe shot up to ~4, as increased returns outweighed the additional volatility seen in the period.

*Who’s next?: Monte Carlo simulation of current hot WSB stocks*

As a next step, we took the latest hot names discussed on the WSB forum and created a Monte Carlo simulation, analyzing expected returns of a new "Reddit portfolio". We focus on SNDL, TLRY, APHA, GME, AMC, BB, MVIS, and ACB. Specifically, we use one year of historical data and 100 simulations over the next 252 trading days. We then compared this to a portfolio fully invested in the S&P 500 ![here](weirong/Monte_Carlo.ipynb). While the S&P 500 simulations are fairly evenly distributed, as expected, the new Reddit portfolio exhibits rather extreme returns, ranging from a **minimum** of 120% to a maximum of 7100%.

*Next Steps: Dogecoin to the moon!*

Given two more weeks to work on this project, we would like to analyze Reddit/social media's impact on other asset classes, particularly crytocurrencies. Dogecoin has been a favorite amongst the WSB community, and several wealthy investors; this would be an interesting asset class to continue our analysis on.
