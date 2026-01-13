# Tamarin General Ledger
## Lightweight, extensible accounting Engine

*Features:*
- Double Entry Accounting
- Supports multiple ledgers
- Account rollup / hierarchy for reporting
- Basic financial reports:
  - Balance Sheet
  - Income Statement
  - Cash Flow Statement
  - Trial Balance
  - Chart of Accounts
  - GL Detail Report
- Supports subledgers like Trade Payables, Trade Receivables, Fixed Assets, Inventory
- User-configurable fiscal year
- Supports 12 or 13 annual accounting periods
- Closing a period summarizes balances for faster reporting
- Configurable autonumbering and transaction prefixes (e.g. INV10001, INV10002, etc.)

*Architecture:*
- Stores debits as positive numbers, credits as negative numbers:  this applies to *all* GL accounts
- enforces *debit+credit=0* integrity
- Currency precision is user configurable (values stores as integers, no use of Decimal module)
- Connectors for SQLite and PostgreSQL
- Transactions are immutable (enforced by SQL triggers) in the database, and checked in the Transaction class
