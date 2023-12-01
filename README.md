# EWI Crypto Index
<img width="45%" height="45%" alt="Screenshot 2023-12-01 at 4 42 03 PM" src="https://github.com/KmiQ/ewi-crypto-index/assets/17998810/e977ac54-768e-4748-be4e-f4896af39ce7">


## Motivation
Investing in cryptocurrencies used to mean spending hours on manual fundamental and technical analysis for each project, trying to guess which ones would succeed. This method was time-consuming, unsustainable, and not in line with my life goals. Then it hit me: there's a limit to losses (_you can only lose up to the total amount of your investment_), but gains are not (_theoretically, there is no ceiling for gains, which explains why some tokens exhibit gains exceeding 1000%_). In other words, while you can only lose what you invest, the potential gains are unlimited. This shift in perspective led me to look at the bigger picture in the crypto market, rather than focusing on individual tokens, I began adopting what I like to call 'a market mindset', a strategy I later discovered is commonly used in venture capital investments. This approach involves zooming out to view the market as a whole. During this process, I was driven by a key question: **If you invest a certain amount, say $x, at time t and distribute it equally across all available crypto tokens, what would be the value of that investment at a later time, t1 (where t1 is greater than t)? Essentially, I wanted to find out if the gains from the successful tokens could outweigh the losses from the less successful ones.**

To find out, I did some backtesting to see if focusing on the market as a whole would generally lead to profits. This led me to see that I needed a better way to keep an eye on the entire crypto market, not just based on Bitcoin's singular representation or Ethereum-only-based indexes. That's why I created the EWI Crypto Index. It's a straightforward metric that reflects the overall condition of the crypto market by including a variety of tokens. I started this index in 2022 to make it easier to analyze crypto investments. It runs daily (automatically) and posts reports on its dedicated [Telegram channel](https://t.me/+1nrLm5ZoNHsxMTYx) and [Twitter account](https://twitter.com/crypto_ewi). I've been using this index for my own crypto investments, and after a year, I've decided to share it with the community, which can probably help to make it better. Below, you'll find more details about how the index is built, maintained, and which improvements are planned for the future.

## Index Goals
- [Measuring] Measure the crypto market performance.
- [Simple] As simple as possible.
- [Trackeable] Easy to track (_build an investment portfolio that tracks the index_).

## Eligibility Criteria
Crypto tokens must meet the following eligibility factors to be eligible as an index constituent:
- [Exchange Listing] Listed on one of the following crypto tokens exchanges:
- - Coinbase
- [BlackList] No restriction at this time. [WIP]
- [Market Capitalization] No restriction at this time. [WIP]
- [Investable Weight Factor (IWF)] No restriction at this time. [WIP]
- [Liquidity] No restriction at this time. [WIP]
- [Financial Viability] No restriction at this time. [WIP]
- [Activity] Consistently trading data about the token for the last 24hr.
- [Volatility] No restriction at this time.

**Reasoning**
The idea behind these rules is to be as inclusive as possible and keep things simple, having a broader representation of the crypto market industry with minimal intervention about who should be considered or not a player. That said, this is still a work in progress and a better job could be done regarding eligibility. IMO the sweet spot is one where we reach a balance between keeping the market mindset and protecting ourselves from non-sense/fake/fraud tokens.

## Index Construction

### Constituent Selection
At each quarter reconstitution, all eligible tokens are selected and form the index. (_see [assets.json](https://github.com/KmiQ/ewi-crypto-index/blob/master/assets.json)_)

### Weighting
The index is an Equal Weighted Index. An equal-weighted index is one where every stock, or crypto-token, has the same weight, and a portfolio that tracks the index will invest an equal dollar amount in each applicable instrument/constituent. As prices move, the weights will shift, and exact equality will be lost. Therefore, an equal-weighted index must be rebalanced from time to time to re-establish proper weighting. At this time, we are doing no rebalancing to keep things simple (one of the foundational goals).

<img width="259" alt="Screenshot 2023-12-01 at 4 08 53 PM" src="https://github.com/KmiQ/ewi-crypto-index/assets/17998810/69dc0402-b79c-4f2a-9430-8be4d1b1a01a">

**Reasoning**
For implementation simplicity, instead of taking `1/N` as the initial weight (_which is the standard in the financial industry_), I'm taking `1`. So the index value on the first day will be `N`, with `N` equal to the amount of constituents in the Index.

### Index Calculation
<img width="510" alt="Screenshot 2023-12-01 at 4 11 02 PM" src="https://github.com/KmiQ/ewi-crypto-index/assets/17998810/0c9cc702-4506-43d5-80e9-f7aedd8ddd33">

Since we are doing **no rebalancing** (see Weighting above), the overall approach to calculate the index at a time `t` is basically to sum up the current index value for each token. This value is determined by how the original founding number/seed (`1` in our case) has evolved as a consequence of token market price moves and no rebalancing.

**Example**

_Market price of constituents A and B:_
|      | Day 1 | Day 2 | Day 3 |
|------|-------|-------|-------|
| **A** | $84   | $79   | $64   |
| **B** | $34   | $53   | $45   |


_Price daily returns of constituents A and B (See equation 3):_
|      | Day 1  | Day 2   | Day 3   |
|------|--------|---------|---------|
| **A** | 0 (0%) | -0.05 (-5%) | -0.19 (-19%) |
| **B** | 0 (0%) | 0.55 (55%)  | -0.15 (-15%) |


_Index value of constituents A and B (See equation 2):_
|      | Day 1 | Day 2 | Day 3 |
|------|-------|-------|-------|
| **A** | 1     | 0.95  | 0.76  |
| **B** | 1     | 1.55  | 1.32  |


_Total Index Value per day (See equation 1):_
- Day 1: TotalIndexValue = 1 + 1 = 2
- Day 2: TotalIndexValue = 0.95 + 1.55 = 2.5
- Day 3: TotalIndexValue = 0.76 + 1.32 = 2.08


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
- - Recalculation (_calculation runs from scratch = first day after index reconstitution_).
- - Technical implementation work is done (_bugs, tasks, updates, etc …_).

## Index Governance
TBD

## Index Policy
TBD

## Index Data
A daily update of the EWI Crypto Index is posted in [Telegram channel](https://t.me/+1nrLm5ZoNHsxMTYx) and [Twitter account](https://twitter.com/crypto_ewi). A daily post looks like the image below:

<img src="https://github.com/KmiQ/ewi-crypto-index/assets/17998810/f63c9900-1721-44ac-8791-67aee4e44d6e" width="25%" height="25%">

If you're interested in using the index for publications, blogs, or newspapers, or if you'd like more granular information, please reach out to `valleycryptostreet@gmail.com`.

## FAQs
**Q: Why no rebalancing?**
The decision behind no-rebalancing is to keep things simple. Rebalancing means a lot of implementation work, and hard work for portfolios to track the index in addition to extra fees, it’s not clear to me in this case, the reward offset the cost. Also, for the crypto market industry, which is just starting, rebalancing means putting out “value” from the winners into the “lossers”, which is not something I’m sure is a good idea at this stage of the market. That said, I’m open to explore the idea of an “annual” rebalancing to facilitate alignment with those portfolios tracking the index with a strategy of investing the same amount of money in every token.

**Q: What is the best way to track this index?**
Since we are doing no rebalancing, the best way to track the index is to replicate the weights and distribute your investment in tokens according to its weights distribution in the index. However, implementing this is not an easy task, that’s why a secondary strategy could be just invest the same amount of money in every token, as if you were tracking an equal weighted index with frequent rebalancing.

## How to contribute
Got ideas or feedback for the EWI Crypto Index? I'd love to hear from you! Feel free to open an issue with any questions or suggestions and we can take it from there.
