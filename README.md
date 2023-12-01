# EWI Crypto Index

## Motivation
Investing "properly" in the cryptocurrency market often demands exhaustive fundamental and technical analyses for each project to predict its future success. This manual effort, while thorough, proved unsustainable and misaligned with my aspirations for a balanced life. This realization brought me to an epiphany: while investment losses are finite, gains hold boundless potential. This perspective shift led me to adopt a "market mindset," focusing on aggregate market behavior rather than individual token performance.

Consider this scenario: if one were to invest an equal sum across the entire spectrum of cryptocurrency tokens at time t, what would the return be at a later time t1? The core question was whether the collective performance of winning tokens could outweigh the underperformers in a straightforward, no-rebalance investment strategy. To address this, I conducted backtesting to determine if a market-centric approach could consistently yield positive outcomes. This experimentation revealed the necessity for a tool to monitor the crypto market's pulse more comprehensively than Bitcoin's singular representation or Ethereum-only-based indexes.

Hence, I devised a simple, yet effective index—a metric designed to encapsulate the vitality of the crypto industry. The EWI Crypto Index is an equal-weighted index that aims to represent the crypto market's overall health by including a diverse range of tokens. It was birthed in 2022 from a desire to simplify investment analysis for the crypto market. Daily updates/reports are posted on the Telegram channel and Twitter account where the index can be tracked/followed. I have been using this metric as an input for personal investment in the crypto market and after one year I decided to share it with the community.

## Index Goals
- [Measuring] Measure the crypto market performance.
- [Simple] As simple as possible.
- [Trackeable] Easy to track (build an investment portfolio that tracks the index).

## Eligibility Criteria
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
The idea behind these rules is to be as inclusive as possible and keep things simple, having a broader representation of the crypto market industry with minimal intervention about who should be considered or not a player. That said, I feel this is still a work in progress and a better job could be done regarding eligibility. IMO the sweet spot is one where we reach a balance between keeping the market mindset and protecting ourselves from non-sense/fake/fraud tokens.

## Index Construction

### Constituent Selection
At each quarter reconstitution, all eligible tokens are selected and form the index.

### Weighting
The index is an Equal Weighted Index. An equal-weighted index is one where every stock, or crypto-token, has the same weight, and a portfolio that tracks the index will invest an equal dollar amount in each applicable instrument/constituent. As prices move, the weights will shift, and exact equality will be lost. Therefore, an equal-weighted index must be rebalanced from time to time to re-establish proper weighting. At this time, we are doing no rebalancing to keep things simple (one of the foundational goals).

Wi=1 for t=0 (first day)
where:
Wi: Weight of constituent i

**Reasoning**
For implementation simplicity, instead of taking 1N as the initial weight (what is the standard in the industry), we are taking 1. So the index value on the first day will be N, with N equal to the amount of constituents in the Index.

### Index Calculation
TotalIndexValue = iIi                                                              (1)
Ii = Ii(1+Ri),        Ii=1  for t= 0                                      (2)
Ri = PiPi - 1,          Ri=0  for t = 0                                  (3)
where:

Ii: Index value of constituent i at time t.
Ii: Index value of constituent i at time t-1.
Ri: Price return of constituent i at time t.
Ri: Market price of constituent i at time t.
Ri: Market price of constituent i at time t-1.

Since we are doing no rebalancing (see Weighting above), the overall approach to calculate the index at a time t is basically to sum up the current index value for each token. This value is determined by how the original founding number/seed (1 in our case) has evolved as a consequence of token market price moves and no rebalancing.

## Index Maintenance
Quarterly Update
- Dates
- - End of April (Q1 Update)
- - End of July (Q2 Update)
- - End of October(Q3 Update)
- - End of January (Q4 Update)
- Tasks
- - Eligibility Criteria is reviewed.
- - Reconstitution.
- - Recalculation (calculation runs from scratch = first day after index reconstitution).
- - Technical implementation work is done (bugs, tasks, updates, etc …).

## Index Governance
TBD

## Index Policy
TBD

## Index Data
A daily update of the EWI Crypto Index is posted in Telegram channel and X/Twitter account. A daily post looks like the image below:
<img src="https://github.com/KmiQ/ewi-crypto-index/assets/17998810/f63c9900-1721-44ac-8791-67aee4e44d6e" width="25%" height="25%">

If you're interested in using the index for publications, blogs, or newspapers, or if you'd like more granular information, please reach out.
Email: your_email@example.com

## FAQs
**Q: Why no rebalancing?**
The decision behind no-rebalancing is to keep things simple. Rebalancing means a lot of implementation work, and hard work for portfolios to track the index in addition to extra fees, it’s not clear to me in this case, the reward offset the cost. Also, for the crypto market industry, which is just starting, rebalancing means putting out “value” from the winners into the “lossers”, which is not something I’m sure is a good idea at this stage of the market. 
That said, I’m open to explore the idea of an “annual” rebalancing to facilitate alignment with those portfolios tracking the index with a strategy of investing the same amount of money in every token.

**Q: What is the best way to track this index?**
Since we are doing no rebalancing, the best way to track the index is to replicate the weights and distribute your investment in tokens according to its weights distribution in the index. However, implement this is not easy task, that’s why a secondary strategy could be just invest the same amount of money in every token, as if you were tracking an equal weighted index with frequent rebalancing.

**Q: How to contribute?**
Just feel free to create an issue with the desired concern/suggestion and we can take it from there.
