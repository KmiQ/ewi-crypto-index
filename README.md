# EWI Crypto Index

An equal weighted index that aims to represent the crypto market's overall health by including a diverse range of tokens.

## Motivation / Why
As part of investing in the crypto market, I was tired of doing manual fundamental + technical analysis for each crypto project, trying to predict whether a project could be a successful one in the following months/years. I realized this manual labor was not sustainable in the long term and was highly time-consuming, so it was not aligned with my personal goals regarding life design.
At some point, I realized that mathematically speaking, losses are capped (you can’t lose more than 100% of your investment), but gains are not (theoretically, there is no ceiling for gains, that’s why you see tokens with gains greater than 10000%). So, I started to think more in terms of the market, I started to develop what I call “a market mindset” to solve this problem. I started to analyze the field with a “market” zoom-out approach. Navigating through this, there were some fundamental questions I was trying to answer:
If at time t, you invest $X, equally distributed around all the crypto tokens, how much money would you have at time t1 (t1 > t)? Do the winners offset the losers in terms of gains?
I was looking for something simple, you enter the “market” at time t, and you exit the market at time t1 (t1>t), with no rebalancing in the middle or any other strategy, how much money would you have? In terms of %, what was your gain/loss? That’s it. I was not interested in the most optimal trading strategy, I was just interested in a simple, low-risk, and winning strategy.
Trying to answer the above questions, I did some backtesting for the crypto market to see if a market mindset could be a long-term winning strategy. As part of this backtesting work, I realized that my approach could be framed as a simple index to measure/track the state of the crypto industry/market, which I feel I needed a lot with the development of a market mindset since the community approach of just taking Bitcoin as the tracker for crypto market health was not sufficient. So, I came up with an index/metric for tracking the crypto market as part of all the work I was doing to educate myself, answer questions, and leverage the time I’m living on.

Also, many current indexes represent Ethereum ecosystem tokens only. 

## Data & Publishing

A daily update of the EWI Crypto Index is posted in Telegram channel and X/Twitter account. A daily post looks like the image below:
<img src="https://github.com/KmiQ/ewi-crypto-index/assets/17998810/f63c9900-1721-44ac-8791-67aee4e44d6e" width="25%" height="25%">

If you're interested in using the index for publications, blogs, or newspapers, or if you'd like more granular information, please reach out.
Email: your_email@example.com

## Index Methodology

### Index Goals
- [Measuring] Measure the crypto market performance.
- [Simple] As simple as possible.
- [Trackeable] Easy to track (build an investment portfolio that tracks the index).

### Eligibility Criteria
Crypto tokens must meet the following eligibility factors to be eligible as an index constituent:
- [Exchange Listing] Listed on one of the following crypto tokens exchanges:
- - Coinbase
- [BlackList] NO be part of the defined blacklist (defined below).
- [Market Capitalization] Total token market capitalization of US$ 50000 or more.
- [Investable Weight Factor (IWF)] No restriction at this time.
- [Liquidity] No restriction at this time.
- [Financial Viability] No restriction at this time.
- [Activity] Consistently trading data about the token for the last three months.
- [Volatility] Volatility in the last 90 days should be less than 200.

**Reasoning**
The idea behind these rules is to be as inclusive as possible and keep things simple, having a broader representation of the crypto market industry with minimal intervention about who should be considered or not a player. That said, I feel this is still a work in progress, and a better job could be done regarding eligibility. IMO the sweet spot is one where we reach a balance between keeping the market mindset and protecting ourselves from non-sense/fake/fraud tokens.

### Index Construction

#### Constituent Selection
At each quarter reconstitution, all eligible tokens are selected and form the index.

#### Weighting
The index is an Equal Weighted Index. An equal-weighted index is one where every stock, or crypto-token, has the same weight, and a portfolio that tracks the index will invest an equal dollar amount in each applicable instrument/constituent. As prices move, the weights will shift, and exact equality will be lost. Therefore, an equal-weighted index must be rebalanced from time to time to re-establish proper weighting. At this time, we are doing no rebalancing to keep things simple (one of the foundational goals).

Wi=1 for t=0 (first day)
where:
Wi: Weight of constituent i

**Reasoning**
For implementation simplicity, instead of taking 1N as initial weight (what is the standard in the industry), we are taking 1. So the index value on the first day will be N, with N equal to the amount of constituents in the Index.
