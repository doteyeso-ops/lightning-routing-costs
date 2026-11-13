# Lightning routing income vs rebalancing cost: which number you are not measuring

A node can be profitable on routing fees and still lose money every month, because the fee line and the rebalancing line live in different tools.

Running a Lightning node produces two ledgers that are rarely read together. On one side, routing fees earned. On the other, what it cost to keep liquidity where the payments needed it - circular rebalances, on-chain opens and closes, and channels that are funded but never route. A node can look busy and still be a subscription to its own curiosity.

## The numbers that decide it

- **Fee income alone is not profit** — Reconciled against rebalancing and channel churn, most small nodes are negative. The fee number is the one every dashboard shows.
- **Channel drag is the invisible cost** — A channel that never routes is capital parked. Multiply the sats by the months it has been idle and that is the real cost of an opinion you had last year.
- **Fee policy decides who routes through you** — Zero fees do not produce volume; they produce volume from people who would not otherwise pay. Price against the opportunity cost of the liquidity.
- **Rebalancing has a market price** — Circular rebalances, submarine swaps and boltz-style services each have a spread. Paying 30% of a month's income to keep one channel balanced is a decision, not an accident.
- **On-chain costs land rarely** — A channel open can cost more than a month of fees. Amortise it or the monthly picture lies.

## How to do it, in order

1. **Pull the fee ledger.** Forwarding history gives fees earned per channel and per direction. Group by channel, not by day.
2. **Pull the cost ledger.** Rebalances, opens, closes, swaps. If it is not recorded, estimate it - the point is to compare, not to be exact.
3. **Compute per-channel P&L.** Fees earned minus the cost of keeping that channel balanced, minus amortised on-chain cost. Most nodes have two profitable channels and ten passengers.
4. **Close the passengers.** Idle channels are the cheapest thing to fix: the capital comes back and the drag goes to zero.
5. **Re-measure after 30 days.** One change at a time. Routing is noisy; a single day is not evidence.

## Questions

**Is routing profitable for a small node?**

Usually not on fees alone once rebalancing and on-chain costs are counted. It becomes positive when you stop funding channels that do not route.

**What does a cost audit consist of?**

The two ledgers reconciled per channel, the drag quantified, and a list of closes and fee-policy changes with the arithmetic shown.

**Do you need custody to audit?**

No. Read-only exports are enough; nothing needs signing.

## If you would rather not do this by hand

l3itcoin has free client-side calculators for routing income, rebalancing cost and channel drag, plus fixed-price reports that reconcile the two ledgers properly.

→ **l3itcoin** — https://l3itcoin.com?utm_source=github&utm_medium=repo&utm_campaign=lightning-routing-costs

Written by the person who builds l3itcoin. The calculators are free and need no account.

---

l3itcoin · Bitcoin and Lightning cost audits · l3itcoin.com
