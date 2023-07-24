# SQL questionnaire

## Setup
Import this [fake database content](mysqlsampledatabase.zip) into your database.

Below you will find a list of questions.

Find out the answer to each question using the dummy data in your database.

**Copy this file** (see: copy raw content) and fill in your queries + answer on the given location in each question.

## START !

### 1) How many customers do we have?
```
<SELECT COUNT(*) FROM reea.customers; >
```

solution: `<your solution here>`


### 2) What is the customer number of Mary Young?
```
< SELECT customerNumber FROM reea.customers WHERE contactFirstName = 'Mary' AND contactLastName = 'Young';>
```

solution: `<your solution here>`

### 3) What is the customer number of the person living at Magazinweg 7, Frankfurt 60528?
```
<select customerNumber FROM reea.customers where addressLine1 = 'Magazinweg 7' or  addressLine2 = 'Frankfurt 60528' or addressLine1 = 'Frankfurt 60528' or addressLine2 = 'Magazinweg'; # ex 3
>
```

solution: `<your solution here>`


### 4) If you sort the employees on their last name, what is the email of the first employee?
```
SELECT email FROM reea.employees  ORDER BY lastName ASC LIMIT 1; >
```

solution: `<your solution here>`

### 5) If you sort the employees on their last name, what is the email of the last employee?
```
<SELECT email FROM reea.employees  ORDER BY lastName DESC LIMIT 1;>
```

solution: `<your solution here>`


### 6) What is first the product code of all the products from the line 'Trucks and Buses', sorted first by productscale, then by productname.
```
<SELECT  LEFT(products.productCode , 3)  from reea.products where productLine= 'Trucks and Buses ' order by productscale, productname;>
```

solution: `<your solution here>`

### 7) What is the email of the first employee, sorted on their last name that starts with a 't'?
```
<SELECT email FROM reea.employees WHERE lastName REGEXP '^[t].*$' ORDER BY lastName ASC LIMIT 1;>
```

solution: `<your solution here>`


### 8) Which customer (give customer number) payed by check on 2004-01-19?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 9) How many customers do we have living in the state Nevada or New York?
```
<SELECT COUNT(*) FROM reea.customers WHERE state = 'NY' OR state = 'NV';>
```

solution: `<your solution here>`


### 10) How many customers do we have living in the state Nevada or New York or outside the united states?
```
<SELECT COUNT(*) FROM reea.customers WHERE state = 'NV' OR state = 'NY' OR customers.country != 'USA';>
```

solution: `<your solution here>`

### 11) How many customers do we have with the following conditions (only 1 query needed):  - Living in the state Nevada or New York OR - Living outside the USA or the customers and with a credit limit above 1000 dollar?
```
<SELECT COUNT(*) FROM reea.customers WHERE state = 'NV' OR state = 'NY' OR customers.country != 'USA' or creditLimit > 1000; >
```

solution: `<your solution here>`


### 12) How many customers don't have an assigned sales representative?
```
<SELECT  count(*) FROM reea.customers where salesRepEmployeeNumber is NULL;>
```

solution: `<your solution here>`

### 13) How many orders have a comment?
```
<SELECT  count(*) FROM reea.orders where orders.comments is  not NULL;>
```

solution: `<your solution here>`


### 14) How many orders do we have where the comment mentions the word "caution"?
```
<SELECT  count(*) FROM reea.orders where  comments like '%caution%';>
```

solution: `<your solution here>`

### 15) What is the average credit limit of our customers from the USA? (rounded)
```
<SELECT ROUND(AVG(creditLimit))  FROM reea.customers where country = 'USA';>
```

solution: `<your solution here>`


### 16) What is the most common last name from our customers?
```
<SELECT contactLastName, count(contactLastName) as test FROM reea.customers  group by contactLastName ORDER BY test DESC limit 1;>
```

solution: `<your solution here>`

### 17) What are valid statuses of the orders?
- [ ] Resolved

- [ ] Cancelled

- [ ] Broken

- [ ] On Hold

- [ ] Disputed

- [ ] In Process

- [ ] Processing

- [ ] Shipped

```
<>
```

solution: `<your solution here>`


### 18) In which countries don't we have any customers?
- [ ] Austria

- [ ] Canada

- [*] China

- [ ] Germany

- [*] Greece

- [ ] Japan

- [ ] Philippines

- [*] South Korea

```
<SELECT country, count(country) as raad FROM reea.customers group by country order by raad desc ;>
```

solution: `<your solution here>`


### 19) How many orders where never shipped?
```
<SELECT status,count(status) as suming FROM reea.orders where  (status = 'Cancelled') and (status='Disputed';>
```

solution: `<your solution here>`

### 20) How many customers does Steve Patterson have with a credit limit above 100 000 EUR?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 21) How many orders have been shipped to our customers?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 22) How much products does the biggest product line have? And which product line is that?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 23) How many products are low in stock? (below 100 pieces)
```
<Your SQL query here>
```

solution: `<your solution here>`

### 24) How many products have more the 100 pieces in stock, but are below 500 pieces.
```
<Your SQL query here>
```

solution: `<your solution here>`


### 25) How many orders did we ship between and including June 2004 & September 2004
```
<Your SQL query here>
```

solution: `<your solution here>`

### 26) How many customers share the same last name as an employee of ours?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 27) Give the product code for the most expensive product for the consumer?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 28) What product (product code) offers us the largest profit margin (difference between buyPrice & MSRP).
```
<Your SQL query here>
```

solution: `<your solution here>`

### 29) How much profit (rounded) can the product with the largest profit margin (difference between buyPrice & MSRP) bring us.
```
<Your SQL query here>
```

solution: `<your solution here>`

### 30) Given the product number of the products (separated with spaces) that have never been sold?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 31) How many products give us a profit margin below 30 dollar?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 32) What is the product code of our most popular product (in number purchased)?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 33) How many of our popular product did we effectively ship?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 34) Which check number paid for order 10210. Tip: Pay close attention to the date fields on both tables to solve this.  
```
<Your SQL query here>
```

solution: `<your solution here>`

### 35) Which order was paid by check CP804873?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 36) How many payments do we have above 5000 EUR and with a check number with a 'D' somewhere in the check number, ending the check number with the digit 9?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 38) In which country do we have the most customers that we do not have an office in?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 39) What city has our biggest office in terms of employees?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 40) How many employees does our largest office have, including leadership?

```
<Your SQL query here>
```

solution: `<your solution here>`


### 41) How many employees do we have on average per country (rounded)?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 42) What is the total value of all shipped & resolved sales ever combined?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 43) What is the total value of all shipped & resolved sales in the year 2005 combined? (based on shipping date)
```
<Your SQL query here>
```

solution: `<your solution here>`


### 44) What was our most profitable year ever (based on shipping date), considering all shipped & resolved orders?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 45) How much revenue did we make on in our most profitable year ever (based on shipping date), considering all shipped & resolved orders?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 46) What is the name of our biggest customer in the USA of terms of revenue?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 47) How much has our largest customer inside the USA ordered with us (total value)?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 48) How many customers do we have that never ordered anything?
```
<Your SQL query here>
```

solution: `<your solution here>`

### 49) What is the last name of our best employee in terms of revenue?
```
<Your SQL query here>
```

solution: `<your solution here>`


### 50) What is the office name of the least profitable office in the year 2004?
```
<Your SQL query here>
```

solution: `<your solution here>`


## Are you done? Amazing!
![](../_assets/clap-clap-clap.gif)
