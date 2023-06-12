## --In this Markdown, I'm creating a Database and using simple SQL queries to pull from said database--

CREATE TABLE cookie_clients (id INTEGER PRIMARY KEY, name TEXT, location TEXT, region TEXT, monthly_orders INTEGER); 

```sql
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


### --Display database ordered by monthly orders
```sql
SELECT * 
FROM cookie_clients
ORDER BY monthly_orders DESC;
```

### --what is the average order from a client?
```sql
SELECT AVG(monthly_orders)
FROM cookie_clients; 
```

### --what 5 clients order the most per month?
```sql
SELECT name, monthly_orders 
FROM cookie_clients
ORDER BY monthly_orders DESC
LIMIT 5;
```

