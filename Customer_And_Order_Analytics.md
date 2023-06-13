## ✨In this SQL, I'm querying a database with multiple tables to quantify statistics about customer and order data✨

### 1. How many orders were placed in January?
```sql
SELECT * 
FROM BIT_DB.JanSales
WHERE length(orderid) = 6
AND orderid <> 'Order ID';
```
In this query we're filtering out all of the blank and incorrect orderIDs. 


### 2. How many of those orders were for an iPhone? 
```sql
SELECT * 
FROM BIT_DB.JanSales
WHERE product = "iPhone" 
AND length(orderid) = 6;
```
<img width="161" alt="Screenshot 2023-06-12 at 9 04 36 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/18a27afb-9b0a-4d2e-a8f7-4799756419ba">


### 3. Select the customer accouint numbers for all of the orders that were placed in February.
```sql
SELECT distinct acctnum
FROM BIT_DB.customers cust
INNER JOIN BIT_DB.FebSales Feb
ON cust.order_id = Feb.orderid
WHERE length(orderid) = 6
AND orderid <> 'Order ID';
```


### 4. Which prodcut was the cheapest one sold in January, and what was the price?
```sql
SELECT product, price
FROM BIT_DB.JanSales
ORDER BY price ASC LIMIT 5;
```
<img width="305" alt="answer for numba 4" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/0411438e-59e8-4d45-945d-3a73156c799a">


### 5. What is the total revenue for each product sold in January?
```sql
SELECT sum(quantity)*price as revenue
, product
FROM BIT_DB.JanSales
GROUP BY product;
```


### 6. Which products were sold in February at 548 Lincoln St, Seattle, WA 98101, how many of each were sold, and what was the total revenue? 
```sql
SELECT sum(quantity), product,
sum(quantity)*price as revenue 
FROM BIT_DB.FebSales
WHERE location = '548 Lincoln St, Seattle, WA 98101';
GROUP BY product;
```
<img width="344" alt="Screenshot 2023-06-12 at 9 07 40 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/9bcc0e2d-ac30-4f06-afcd-e099010ca9d0">


### 7. How many customers ordered more than 2 products at a time in February, and what was the average amount spent for those customers? 
```sql
SELECT count(distinct cust.acctnum),
avg(quantity*price)
FROM BIT_DB.FebSales Feb
LEFT JOIN BIT_DB.customers cust
ON FEB.orderid = cust.order_id
WHERE Feb.Quantity > 2
AND length(orderid) = 6
AND orderid <> 'Order ID';
```
<img width="378" alt="answer for q 7" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/50054e25-87f2-4f7b-9c7d-3d432fc27f1c">


### 8. Which locations in New York received at least 3 orders in January, and how many orders did they each receive?
```sql
SELECT distinct location, count(orderID)
FROM BIT_DB.JanSales
WHERE location LIKE '%NY%'
AND length(orderid) = 6
AND orderid <> 'Order ID'
GROUP BY location
HAVING count(orderID)>2;
```
<img width="431" alt="poop" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/cb81eb5f-7f3b-4b3d-9e61-195123692bda">


### 9. How many of each type of headphone were sold in February?
```sql
SELECT sum(Quantity) as quantity, Product
FROM BIT_DB.FebSales
WHERE Product like '%Headphones%'
GROUP BY Product;
```
<img width="426" alt="Screenshot 2023-06-12 at 9 10 36 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/d9e2b2fb-f046-4f89-b801-3d993bba5a53">


### 10. What was the average amount spent per account in February? 
```sql
SELECT avg(quantity*price)
FROM BIT_DB.FebSales Feb
LEFT JOIN BIT_DB.customers cust
ON FEB.orderid = cust.order_id
WHERE length(orderid) = 6
AND orderid <> 'Order ID';
```
<img width="188" alt="Screenshot 2023-06-12 at 9 11 29 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/a1a35535-62a4-4f03-9597-c2591eb2f19f">


### 11. What was the average quantity of products purchased per account in February?
```sql
SELECT sum(quantity)/count(cust.acctnum)
FROM BIT_DB.FebSales Feb
LEFT JOIN BIT_DB.customers cust
ON FEB.orderid = cust.order_id 
WHERE length(orderid) = 6
AND orderid <> 'Order ID';
```


### 12. Which product brought in the most revenue in January and how much revenue did it bring in total?
```sql
SELECT product, sum(quantity*price)
FROM BIT_DB.JanSales
GROUP BY product
ORDER BY sum(quantity*price) DESC
LIMIT 1;
```
<img width="316" alt="Screenshot 2023-06-12 at 9 12 36 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/9970771d-b386-4995-a4c3-ba52e357c100">


## Thank you for your time! 👩🏻‍💻 





































