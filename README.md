# The Reddit Trade
## An analysis of social media’s impact on stock performance

*Fundamental setup: weak metrics for GME, a brick and mortar video game company during a global pandemic*

Gamestop engages in retail selling video games, consumer electronics and merchandise related to video games in United States, Canada, & Europe. As a brick and mortar video game retailer in the middle of global pandemic, the company displays weak fundamentals. We analyze these ![here](Ziggy/fundamental_story.ipynb). We see...

*Technical setup: hedge funds had accumulated a very large short position*

As a result of the weak fundamentals, hedge funds established a large short position (more than 100% of the float) to bet against the stock, really accelerating at the end of last year, into January. We pull historical Bloomberg data to create a "short trend" graph ![here](weirong/GME_short.ipynb).

*Sentiment analysis: daily movements in stock prices impacted by WSB posts*

Wanting to "stick it to the man" and "fight" the hedge funds, retail investors began buying up GME shares at very cheap prices. A notable forum for discussing stocks amongst these investors is the Reddit wallstreetbets (WSB) page. We pull posts from this forum over the second half of January to early February to analyze how sentiment in the forum has driven stock price performance amongst most talked about names (not just GME, but also AMC, BBBY, NOK, and BB). We create a "wordcloud" highlighting popularity of particular words in titles of WSB posts and then compare daily price movements in an equal weighted portfolio of these "Reddit stocks" to daily sentiment from the forum. We use Kaggle data, along with the praw Reddit api, and nltk NLP package to analyze sentiment ![here](Victor/reddit_processing.ipynb) and ![here](Victor/reddit_analysis.ipynb).

*Returns, betas, and sharpes*

The resulting stock movements in these names created some very interesting statistical results. We look at rolling 120-day betas as well as Sharpe ratios of these Reddit names vs the S&P 500, individually and as an equal weight portfolio ![here](Yuttakarn/Risk.ipynb). We see betas get to extremes of -5; on days these names did particularly well, the market overall was selling off as fear of bubbles, extended leverage, and regulatory repercussions saw the rest of the market underperform (and vis-a-versa). Of note, Sharpes using one year of data were consistently greater in these Reddit names than the overall market, and just looking at the last month of data, GME's Sharpe shot up to ~4 as increased returns outweighed the additional volatility seen in the period.

*Who’s next?: Monte Carlo simulation of current hot WSB stocks*

As a next step, we took the latest hot names discussed on the WSB forum and created a Monte Carlo simulation, analyzing expected returns of a new "Reddit portfolio". We focus on SNDL, TLRY, APHA, GME, AMC, BB, MVIS, and ACB. Specifically, we use one year of historical data and 100 simulations to simulate the next 252 trading days. We then compared to portfolio full invested in the S&P 500 ![here](weirong/Monte_Carlo.ipynb). While the S&P 500 simulations are fairly evenly distributed, as expected, the new Reddit portfolio exhibits rather extreme returns, ranging from a ##minimum## of 119% to a maximum of 7100%.


