# SQL
Overview of Basic commands in SQL

1) Creating tables

  CREATE TABLE customers (id INTEGER PRIMARY KEY, name TEXT, age INTEGER, weight REAL)
  
  CREATE TABLE customers (id INTEGER PRIMARY KEY, age INTEGER); Using primary keys
  
2) Inserting data

  INSERT INTO customers VALUES (73, "Brian", 33);
  
  INSERT INTO customers (name, age) VALUES ("Brian", 33);
  
3) Querying data

  SELECT * FROM customers;  (everything)
  
  SELECT * FROM customers WHERE age > 21; (condition)
  
  SELECT * FROM customers WHERE age < 21 AND state = "NY";  (multiple condition)
  
  SELECT * FROM customers WHERE plan IN ("free", "basic"); (IN condition)
  
  SELECT name, age FROM customers; (specific column)
  
  SELECT * FROM customers WHERE age > 21 ORDER BY age DESC; (order)
  
  SELECT name, CASE WHEN age > 18 THEN "adult" ELSE "minor" END "type" FROM customers;  (different cases)
  
4) Aggregating data
  
  SELECT MAX(age) FROM customers;  (maximum)
  
  SELECT gender, COUNT(*) FROM students GROUP BY gender;  (count)
  
5) Joining related tables

  SELECT customers.name, orders.item FROM customers JOIN orders ON customers.id = orders.customer_id; (inner join-intersection)
  
  SELECT customers.name, orders.item FROM customers LEFT OUTER JOIN orders ON customers.id = orders.customer_id; (outer join-union)
  
6) Updating and deleting data

  UPDATE customers SET age = 33 WHERE id = 73;  (update)
  
  DELETE FROM customers WHERE id = 73;  (delete)
