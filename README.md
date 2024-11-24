## Sales Insights Data Analysis Project

### Data Analysis Using SQL

1. Retrieves all columns and rows from the `customers` table.

    `SELECT * FROM customers;`

1. Counts the total number of rows (customers) in the `customers` table.

    `SELECT count(*) FROM customers;`

1. Retrieves all transactions from the `transactions` table where the `market_code` is `Mark001` (Chennai market).

    `SELECT * FROM transactions where market_code='Mark001';`

1. Retrieves a unique list of product codes sold in the Chennai market `(Mark001)`.

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Retrieves all transactions from the `transactions` table where the currency is `USD.

    `SELECT * from transactions where currency="USD"`

1. Retrieves all columns from both the `transactions` and `date` tables for orders placed in the year 2020.

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Calculates the total sales amount for the year 2020 in transactions where the currency is either INR or USD.
    `SELECT SUM(transactions.sales_amount)
    FROM transactions
    INNER JOIN date ON transactions.order_date=date.date
    where date.year=2020
    and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Calculates the total sales amount for January 2020, considering only transactions with currencies INR or USD.

   `SELECT SUM(transactions.sales_amount)
   FROM transactions
   INNER JOIN date ON transactions.order_date=date.date
   where date.year=2020
   and date.month_name="January"
   and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Calculates the total sales amount for the year 2020 in the Chennai market `(Mark001)`

   `SELECT SUM(transactions.sales_amount)
   FROM transactions
   INNER JOIN date ON transactions.order_date=date.date
   where date.year=2020
   and transactions.market_code='Mark001';`


