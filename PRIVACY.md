# Privacy Policy

See `README.md` for a description of how the service operates. 

This software uses the YNAB API to:
- replicate transactions from one user to another user
- to create a reconciliation transaction at one of the user's request

To accomplish this, it uses dedicated flags, budgets, memos, and accounts ("features"). The "state" of the software is stored in the user's YNAB account using these features.

The software will keep a record of:
- The user's credentials for `expense-sharing-for-ynab` including: a name, email, password hash, and OAuth details
- Access logs to ensure the security of the system (IP address, login attempts)
- The user group's preferences (shared budget selection, flag selection, tracking account selection, reconciliation split amount)[^1]

[^1]: these will include YNAB data details such as ID numbers so the service can refer to them in future

Individual transactions are not databaseded - only the minimum amount of YNAB data will be stored by this service in order to operate it (i.e.: ID numbers for "features"). 

The data collected by this service will not be passed to a third-party. 
