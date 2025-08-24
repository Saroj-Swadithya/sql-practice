## Q1: Show name, continent, and population

Show the name, continent, and population of all countries.

```sql
SELECT name, continent, population FROM world;
```
---

## Q2: Large Countries

Show the name for the countries that have a population of at least 200 million.

```sql
SELECT name FROM world
 WHERE population >= 200000000;
```
---

## Q3: Per capita GDP

Give the name and the per capita GDP for those countries with a population of at least 200 million.

```sql
SELECT name, (gdp/population) AS 'per capita GDP'
FROM world
WHERE population >= 200000000;
```
---

## Q4: South America in millions

Show the name and population in millions for the countries of the continent 'South America'.

```sql
SELECT name, population/1000000
FROM world
WHERE continent='South America';
```
---

## Q5: France, Germany, Italy

Show the name and population for France, Germany, Italy.

```sql
SELECT name, population 
FROM world
WHERE name IN ('France', 'Germany', 'Italy');
```
---

## Q6: Countries with "United"

Show the countries which have a name that includes the word 'United'.

```sql
SELECT name FROM world
WHERE name LIKE "%United%";
```
---

## Q7: Two ways to be big

A country is big if it has an area of more than 3 million sq km or it has a population of more than 250 million.

```sql
SELECT name, population, area 
FROM world
WHERE area > 3000000 OR population > 250000000;
```
---


## Q8: One or the other (but not both)

Show the countries that are big by area (more than 3 million) or big by population (more than 250 million) but not both.

```sql
SELECT name, population, area
FROM world
WHERE area > 3000000 XOR population > 250000000;
```
---


## Q9: Rounding in South America
Show the name and population in millions and the GDP in billions for the countries of the continent 'South America'. Use ROUND to 2 decimals.
```sql
SELECT name, ROUND(population/1000000.0,2),
             ROUND(gdp/1000000000.0,2)
FROM world
WHERE continent='South America';
```
---


## Q10: Trillion dollar economies

Show the name and per-capita GDP for those countries with a GDP of at least 1 trillion. Round per capita GDP to nearest 1000.
```sql
SELECT name, ROUND(gdp/population,-3)
FROM world
WHERE gdp >= 1000000000000;
```
---


## Q11: Name and capital have the same length

Show the name and capital where the name and the capital have the same number of characters.
```sql
SELECT name, capital
FROM world
WHERE LENGTH(name) = LENGTH(capital);
```
---


## Q12: Matching first letter (name vs capital)

Show the name and the capital where the first letters of each match. Don’t include countries where the name and the capital are the same word.
```sql
SELECT name, capital
FROM world
WHERE LEFT(name,1) = LEFT(capital,1) 
  AND name <> capital;
```
---


## Q13: Country with all vowels

Find the country that has all the vowels (a, e, i, o, u) and no spaces in its name.
```sql
SELECT name
FROM world
WHERE name LIKE '%a%' 
  AND name LIKE '%e%' 
  AND name LIKE '%i%' 
  AND name LIKE '%o%' 
  AND name LIKE '%u%'
  AND name NOT LIKE '% %';
```
