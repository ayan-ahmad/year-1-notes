## Storing Data
### Primary Key
Each entry into a database requires a primary key. The primary key will be unique so that you can access each individual entry.
### Entity Relationship Diagram (ERD)
### Relational Model
- Data is sorted in tables
- Entries have primary keys, when used from other tables they are called foreign keys

See more here [[Database diagram#ERD]]
## SQL Queries
### Single Table
#### Creation
To create a table we use the keyword `CREATE TABLE` 
```SQL
CREATE TABLE Employees (
    ID INT PRIMARY KEY,
    Name VARCHAR(30),
    Age INT,
    Salary DECIMAL(10, 2)
);
```
### Selection
To select data from a table, we use the `SELECT`
```SQL
SELECT * FROM Employees;
```
### Insertion
To insert data into a table, we use the `INSERT INTO` statement.
```sql
INSERT INTO Employees (ID, Name, Age, Salary)
VALUES (1, 'John Doe', 30, 50000.00);
```
### Deletion
To delete data from a table, we use the `DELETE` statement. For example:
```sql
DELETE FROM Employees WHERE ID = 1;
```
### Multi Table
#### Join
To combine rows from two or more tables based on a related column, we use the `JOIN` statement.
```sql
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```
#### Union
To combine the result set of two or more `SELECT` statements, we use the `UNION` operator.
```sql
SELECT column_name FROM table1
UNION
SELECT column_name FROM table2;
```
## Object Relational Mappers (ORM)
ORMs are a programming technique **
### DJango
If we want to create a table in DJango we can do it like so:
```python
from django.db import models

class User(models.Model):
	name = models.CharField(**)
	**
```
## Request-Response Cycle
## Model View Controller (MVC)
The base of DJango can be simplified into 3 basic components:
- Model – The data that we store and manage in a database and tables
- View – The view shown to the users made with HTML, CSS & JS
- Controller – The decision making and routing that happens through the code in the backend
