# (Opinionated) Expense Sharing for YNAB

**TL;DR**: tooling to make separate but equitable finances simple. Granular per-transaction visibility for all shared transactions with arbitrary expense splitting for end-of-period reconciliation. 

Does not require a shared credit card or chequing account; separate but equitable finances made easy. 

Set your `YNAB_API_ACCESS_TOKEN` in `.env`. This is a personal access token generated in the [Developer Settings](https://app.ynab.com/settings/developer) page in YNAB. It grants full access to your account; don't use this software in a situation where random people on the Internet can interact with it. 

----

This software enables expense sharing for two users. For simplicity, we'll call the two users the expense payer[^1] and the expense receiver[^2].

It is assumed that both users are using "YNAB Together" with separate budgets, and one of them knows a bit about using software. This simplifies API authentication; this code would have to support an OAuth workflow to make it a non-technical user friendly application for multiple YNAB accounts. 

[^1]: the user that paid an expense that is to be shared
[^2]:  both users will be in both roles over time, assuming they both pay for shared expenses. 

It is required that both users share common shared budget categories - i.e.: "Shared Groceries".

# Process
This software uses the YNAB API to find transactions that are flagged as shared in the expense payer's account. It replicates them under a fictional tracking account for the expense receiver. This gives the expense receiver visibility into what has been spent as a group. 

At a time of either user's choosing, these tracking account balances can be reconciled: either via an even split, or a percentage share. This generates a reconciliation transaction that is split across each shared budget category. The tracking account balance will drift from zero over time depending on the reconciliation split chosen. 

This enables both users to budget separately, while also having granular visibility about shared budget amounts without having to do a lot of extra book keeping. 