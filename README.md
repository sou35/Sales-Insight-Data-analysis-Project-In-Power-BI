# Sales-Insight-Data-analysis-Project-In-Power-BI
## Instructions to setup mysql on your local computer
1.Follow step in this Documentation to install mysql on your local computer [MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/5.7/en/)

2.SQL database dump is in db_dump.sql file above. Download [db_dump.sql](db_dump.sql) file to your local computer and import it .

## Data Analysis Using SQL
### Show all customer records
```
SELECT * FROM customers;
```

### Show total number of customers
```
SELECT count(*) FROM customers;
```

### Show transactions for Chennai market (market code for chennai is Mark001)
```
SELECT * FROM transactions where market_code='Mark001';
```
### Show distrinct product codes that were sold in chennai
```
SELECT distinct product_code FROM transactions where market_code='Mark001';
```
### Show transactions where currency is US dollars
```
SELECT * from transactions where currency="USD"
```

### Show transactions in 2020 join by date table
```
SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;
```
### Show total revenue in year 2020,
```
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date
 where date.year=2020 and transactions.currency='INR\r' or transactions.currency='USD\r';
```
### Show total revenue in year 2020, January Month,
```
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");
```
### Show total revenue in year 2020 in Chennai
```
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

```
### Duplicate currency value
```
'select*from transactions where transactions.currency*'USD\r' or transactions.currency*'USD';
```
```
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date
 where date.year=2020 and (transactions.currency='INR\r' or transactions.currency='USD\r');
 ```
 ```
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date
 where date.year=2020 and date.month_name='January' and (transactions.currency='INR\r' or transactions.currency='USD\r');
 ```
