## ✨In this Markdown, I'm creating a Database and using simple SQL queries to pull from said database✨

```sql
CREATE TABLE cookie_clients (id INTEGER PRIMARY KEY, name TEXT, location TEXT, region TEXT, monthly_orders INTEGER); 

INSERT INTO cookie_clients VALUES (1, "Crumbl", "Salt_Lake_City", "Western", 5);
INSERT INTO cookie_clients VALUES (2, "Chip", "Los_Angeles", "Western", 17);
INSERT INTO cookie_clients VALUES (3, "Crave", "Memphis", "Southeastern", 24);
INSERT INTO cookie_clients VALUES (4, "Misses_Kisses", "Tampa", "Southeastern", 12);
INSERT INTO cookie_clients VALUES (5, "Gorgina_Cookies", "Oakland", "Western", 34);
INSERT INTO cookie_clients VALUES (6, "Massive_Chunk", "Milwaukee", "Midwestern", 10);
INSERT INTO cookie_clients VALUES (7, "Salt_N_Sprinkles", "New_Jersey", "Northeastern", 9);
INSERT INTO cookie_clients VALUES (8, "Doughlicious", "Columbus", "Midwestern", 20);
INSERT INTO cookie_clients VALUES (9, "Lehi_Cookie_Co", "Lehi", "Western", 15);
INSERT INTO cookie_clients VALUES (10, "Cookie_Company", "Orlando", "Southeastern", 31);
```
Here I have a created a simple database that is now available for querying!


### --Display database ordered by monthly orders
```sql
SELECT * 
FROM cookie_clients
ORDER BY monthly_orders DESC;
```
<img width="547" alt="Screenshot 2023-06-12 at 2 02 25 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/9231a712-34f6-4d29-bf64-51d4d2a808a9">

In this query, I'm selecting all in the Database and organizing it so that the cookie companies who order the most every month are the first to display. 


### --what is the average order from a client?
```sql
SELECT AVG(monthly_orders)
FROM cookie_clients; 
```
<img width="175" alt="Screenshot 2023-06-12 at 2 03 02 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/fd22b722-a2cf-4f52-a088-bf18597fe1a3">

This query allows us to see the average monthly orders from each cookie company. 


### --what 5 clients order the most per month?
```sql
SELECT name, monthly_orders 
FROM cookie_clients
ORDER BY monthly_orders DESC
LIMIT 5;
```
<img width="276" alt="Screenshot 2023-06-12 at 2 03 54 PM" src="https://github.com/heavenmhall/SQL-Portfolio/assets/136202944/4bb5f852-a304-4611-a19a-a420ae4ec7f6">

This final query is giving us the top 5 cookie companies that order the most in a month. 
