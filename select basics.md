# Q1: Population of Germany
Show the population of **Germany**:
**Query**
```sql
SELECT population FROM world
  WHERE name = 'Germany';
```
---

# Q2: Checking a list  

The word `IN` allows us to check if an item is in a list.  
Show the name and the population for **Sweden, Norway, and Denmark**.

**Query**
```sql
SELECT name, population FROM world
  WHERE name IN ('Sweden', 'Norway', 'Denmark');
```
---

# Q3: Just the right size

show the country and area for countries with an area between 200,000 and 250,000.

**Query**
```sql
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000;
```
