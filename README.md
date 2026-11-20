# OKX Funding Rate: How Often Is It Settled, Who Pays Whom, and What Does It Actually Cost You? (4h vs 8h, With a $1,000 Example)

A positive OKX funding rate means longs pay shorts, and a negative rate means shorts pay longs. Settlement runs on each contract's own schedule: 8 hours on most pairs, 4 hours on a large minority, and the EEA X-Perps help page describes an 8-hour cycle for that product. You can see the current rate, the estimated next settlement time and the payment history on any contract page under **Info → Funding rate**.

Three things the rate number by itself won't tell you: which interval your contract uses, how the debit is calculated from position value rather than the margin you posted, and why the annualized figures floating around are arithmetic extrapolations rather than income you can lock in.

> **Quick read:** check the funding interval before the rate. The same 0.01% costs twice as much per day on a 4-hour contract as on an 8-hour one. 👉 [Open OKX to check the live funding rate on the contract you trade](https://okx.com/join/CASH20)

## OKX funding mechanics at a glance

OKX is an exchange, so there is no monthly plan or subscription tier to compare. The equivalent here is the settlement spec of the contract you're trading.

| Mechanic | What OKX documents | Scope |
| --- | --- | --- |
| Payment direction | Positive rate: longs pay shorts. Negative rate: shorts pay longs | All perpetuals |
| Settlement interval | 8h default; some contracts use 1h, 2h or 4h; EEA X-Perps page states every 8 hours | Set per contract |
| Calculation base | Position value (quantity × contract specifications × mark price) | USDT-settled contracts |
| Exchange cut | None inside the funding mechanism; trading fees billed separately | All perpetuals |
| Who participates | Positions open at the actual assessment | All perpetuals |
| Where to check | App: Info → Funding rate. Web: contract header → Funding rate | All perpetuals |

## What an OKX funding rate actually is

The funding rate is the proportion used to calculate a transfer between long and short perpetual positions; the funding fee is the amount that actually moves. Perpetuals have no expiry date, so funding changes the cost of holding either side and nudges the contract price back toward its spot reference.

Funding is separate from trading fees. OKX organizes the transfer between longs and shorts and takes no service fee inside that mechanism. Your maker and taker fees are charged on top, when you open and when you close.

The transfer lands in your collateral equity. Paying funding reduces the equity backing the position and, with everything else unchanged, can move it closer to risk thresholds; receiving funding adds to it. This is tracked separately from unrealized price P&L, which is why a position can show a small price gain and still see its margin cushion thin out over a long hold.

## How often does OKX settle funding? 4h vs 8h

It depends on the contract, and the sources describe different levels of generality. OKX's general explainer, updated 12 November 2026, uses eight hours as the default and notes that some contracts settle every one, two or four hours, with rule-based adjustments possible. The EEA X-Perps help page states that X-Perps funding is settled every 8 hours for that product. A third-party tracker's 17 November 2026 snapshot counted 456 OKX perpetual pairs, split into 212 on a 4-hour cycle and 244 on 8 hours.

| Source and scope | Interval stated | Applies to |
| --- | --- | --- |
| OKX Learn, updated 12 Nov 2026 | 8h default; some 1h/2h/4h | Perpetual contracts generally, as set by product rules |
| OKX Help, EEA X-Perps (page updated 14 Aug 2026) | Every 8 hours | X-Perps offered in the EEA |
| Yieldo snapshot, 17 Nov 2026 | 212 pairs at 4h, 244 pairs at 8h | 456 tracked OKX perpetuals |

Eight hours is the common case, not a platform-wide rule. The contract detail page is the authority: it carries the current funding rate, the estimated next funding time and the historical funding data for that specific pair. Other product lines run their own accrual and settlement methods, so an interval you read on one product page doesn't transfer to another.

## Who pays whom

The sign of the rate decides the direction, and the size decides the amount.

| Rate sign | Pays | Receives | What it usually reflects |
| --- | --- | --- | --- |
| Positive | Longs | Shorts | Perpetual trading above its spot reference |
| Negative | Shorts | Longs | Perpetual trading below its spot reference |

Direction isn't fixed for the life of your position. A rate can flip between settlements, and over several periods your receipts offset your payments, which is why a single settlement number is a poor estimate of what a week of holding costs.

## How much you actually pay: the $1,000 example

The fee for one settlement is position value multiplied by the absolute value of the rate. Take two traders holding equal and opposite positions, each assessed at 1,000 USDT of position value across three settlements:

| Settlement | Rate | Trader A (long) | Trader B (short) |
| --- | --- | --- | --- |
| First | +0.01% | Pays 0.1 USDT | Receives 0.1 USDT |
| Second | +0.03% | Pays 0.3 USDT | Receives 0.3 USDT |
| Third | −0.02% | Receives 0.2 USDT | Pays 0.2 USDT |
| Net |  | Pays 0.2 USDT | Receives 0.2 USDT |

The assessment base is the position value under the contract's rules, not the margin behind it. A 1,000 USDT position opened with 100 USDT of collateral is still assessed on 1,000 USDT. For USDT-settled contracts, that value comes from quantity, contract specifications and the mark price, the platform's calculation reference, rather than the last traded price on the book.

Two levers change the number. Doubling the absolute rate doubles the transfer: +0.03% moves three times what +0.01% moves, and the sign only reverses who sends it. Changing the interval changes the total: with a constant rate, 0.01% every eight hours comes to 0.03% of position value per day across three settlements, while 0.002% every hour comes to 0.048% across twenty-four. The hourly contract looks cheaper per settlement and costs more per day.

## Where to check the rate on OKX

In the app: open OKX, choose **Exchange** mode, pick any pair that supports Perps, go to **Info**, then tap **Funding rate** on the right. On the web: open a perps pair and select **Funding rate** in the main header area of the contract page.

Three details trip people up.

The displayed rate updates before settlement, and the actual transfer uses the product's final settlement rate. If your contract is trading below spot right now, the final rate still doesn't have to turn negative, because the rate is built from observations across a window rather than the current spread alone.

The countdown on screen isn't proof that settlement is finished. Processing takes time, and eligibility is judged on whether you held the position at the actual assessment, not on what the timer showed.

The rate itself combines premiums observed over a period, interest parameters, limits and the settlement interval, with the observations weighted and normalized to that interval. That structure is why a rate can stay positive while price drifts.

👉 [Register on OKX through this link to view the current welcome terms](https://okx.com/join/CASH20)

## The annualized number is not a yield

Annualized columns multiply the current hourly rate by 8,760. That's all they do. The rate resets at every settlement, so the result describes a moment, not a contract you can hold for a year.

The 17 November 2026 snapshot shows HUMA at −0.108299% per hour, displayed as **−948.70% annualized**. Nobody is paying or collecting that over twelve months unless the rate stays exactly there for 8,760 hours, which it won't. Treat such figures as a measure of how crowded one side of the book is right now.

Interval frequency matters more than the headline rate. A 0.01% rate costs **0.06% per day** on a 4-hour contract with six settlements, and **0.03% per day** on an 8-hour contract with three. Two contracts can display the same number and differ by a factor of two in daily cost, and most explanations that quote "every eight hours" never touch that gap.

👉 [Check OKX's current perpetual funding rates and next settlement time](https://okx.com/join/CASH20)

## Current OKX funding snapshot

The following comes from Yieldo's tracker on 17 November 2026, refreshed every ten minutes. It is third-party data, not an OKX quote, and every number will have moved by the time you read this.

Across 456 tracked perpetual pairs, the average absolute rate was 0.002111% per hour. The widest positive rate sat on FWDI at **+0.208073%** per 8-hour period, with longs paying. The most negative was HUMA at **−0.433198%** per 4-hour period, with shorts paying. Other extremes in the same snapshot: SOPH −0.382372%, UNITREE −0.280405%, INIT −0.193845%, HYUNDAI +0.122167% and CXMT +0.108496%.

For the majors, hourly-normalized rates on the same snapshot looked like this:

| Pair | OKX (%/hour) | Binance (%/hour) |
| --- | --- | --- |
| BTC | +0.000226 | +0.000039 |
| ETH | −0.000314 | +0.000389 |
| SOL | −0.001724 | −0.001597 |
| BNB | +0.000605 | 0.000000 |
| XRP | −0.000607 | −0.000417 |
| ADA | −0.001126 | −0.000093 |
| DOGE | −0.000090 | −0.000409 |
| HYPE | +0.000164 | −0.000188 |

On liquid pairs these numbers are small enough that trading fees and spread will usually decide whether a carry trade is worth doing. The interval column is per row, so compare per-hour values rather than the per-period figures.

## Funding-rate carry: what the pitch leaves out

A delta-neutral carry means going long where funding is low or negative and short where it is high, so the two legs offset price exposure and you collect the rate difference. Both legs need margin, on two venues, with two sets of fees. It is market-neutral, not risk-free.

OKX runs a unified account, where spot, margin and perpetuals share one collateral pool. That's efficient when you run several hedged legs, and it's also how a losing perpetual can pull collateral away from a carry position that was otherwise fine. Cross-margin shares the risk as well as the capital.

The annualized column isolates funding only. It excludes maker and taker fees, which on perpetuals are charged when you open and again when you close. Third-party fee trackers put the regular futures tier at 0.02% maker and 0.05% taker as of early November 2026; your own account page is the number that applies to you, and VIP tiers change it.

## FAQ

**What does a negative funding rate mean on OKX?**
Shorts pay longs. It usually means the perpetual is trading below its spot reference, so holding a short costs money and holding a long earns it.

**Can I avoid funding by closing before settlement?**
Yes, if you're flat at the assessment. A trader who opens after one assessment and closes before the next participates in neither transfer. Closing a few minutes early only works if the position is actually closed; a pending order or a countdown doesn't count.

**Why is the rate shown different from what I was charged?**
The displayed rate keeps updating and the transfer uses the final settlement rate. Your rate is also applied to your position value at assessment, which may have changed since you last looked.

**Does OKX charge a fee on funding?**
No. The payment moves between longs and shorts, and OKX takes no service fee inside the mechanism. Trading fees are separate and apply to your orders.

**Can a funding rate predict price?**
No. It explains holding costs and how far the contract sits from spot, and its sign or size alone doesn't establish where price goes next.

## Before you open the position

If you're holding for days, the interval and the mark-price base decide your cost, so check the contract's funding interval and next settlement time before sizing up. If you're holding through a strongly positive rate, multiply the rate by the number of daily settlements to get your daily drag, and compare that to what you expect from the trade.

If you're running carry, the cross-venue gap on per-hour numbers, the depth on both books and both fee schedules matter more than any annualized figure. A rate that looks enormous on a thin altcoin often isn't executable at size.

Two things to confirm on the contract page before you commit: the settlement interval that pair actually uses, and when the next settlement lands.

👉 [Use this OKX link to compare the funding interval on the contract you plan to hold](https://okx.com/join/CASH20)
