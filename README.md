# Tamarin General Ledger Engine
Lightweight, extensible Accounting Engine

*Features:*
- Supports multiple ledgers
- Account rollup / hierarchy for reporting
- Currency precision configurable
- Basic financial reports: Balance Sheet, Income Statement, Cash Flow Statement, Trial Balance, Chart of Accounts, GL Detail Report
- Supports subledgers like Trade Payables, Trade Receivables, Fixed Assets, Inventory
- Supports 12 or 13 annual accounting periods
- Closing a period summarizes balances for faster reporting
- Configurable autonumbering and transaction prefixes (e.g. INV10001, INV10002, etc.)

*Architecture:*
- Stores debits as positive numbers, credits as negative numbers:  this applies to *all* GL accounts
- Connectors for SQLite and PostgreSQL
- enforces *debit+credit=0* integrity
- Transactions are immutable (enforced by SQL triggers) in the database, and checked in the Transaction class
