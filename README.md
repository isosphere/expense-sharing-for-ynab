# (Opinionated) Expense Sharing for YNAB

**TL;DR**: granular per-transaction visibility for all shared transactions with arbitrary expense splitting for end-of-period reconciliation. 

Does not require a shared credit card or chequing account. 

Set your `YNAB_API_KEY` key in `.env`.

----

This software enables expense sharing for two users. For simplicity, we'll call the two users the expense payer[^1] and the expense receiver, though both users will be in both roles over time, assuming they both pay for shared expenses. 

[^1]: the user that paid an expense that is to be shared

This software uses the YNAB API to find transactions that are flagged as shared in the expense payer's account and replicates them under a fictional tracking account for the expense receiver. This gives the 
expense receiver visibility into what has been spent as a group. It is required that both users share common shared budget categories - i.e.: "Shared Groceries".

At a time of either user's choosing, these tracking account balances can be reconciled: either via an even split, or a percentage share. This generates a reconciliation transaction that is split across each shared budget category. The tracking account balance will drift from zero over time depending on the reconciliation split chosen. 


This enables both users to budget separately, while also having granular visibility about shared budget amounts. 

