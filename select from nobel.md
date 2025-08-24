```sql
1. Winners from 1950  

Query:

SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950;

2. 1962 Literature Winner

Query:

SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'literature';

3. Albert Einstein’s Prize

Query:

SELECT yr, subject
  FROM nobel
 WHERE winner = 'Albert Einstein';

4. Peace Winners Since 2000

Query:

SELECT winner
  FROM nobel
 WHERE subject = 'peace'
   AND yr >= 2000;

5. Literature in the 1980s

Query:

SELECT *
  FROM nobel
 WHERE subject = 'literature'
   AND yr >= 1980
   AND yr <= 1989;

6. Presidential Winners

Query:

SELECT *
  FROM nobel
 WHERE winner IN ('Theodore Roosevelt',
                  'Thomas Woodrow Wilson',
                  'Jimmy Carter',
                  'Barack Obama');

7. Winners Named John

Query:

SELECT winner
  FROM nobel
 WHERE winner LIKE 'John%';

8. Physics (1980) & Chemistry (1984)

Query:

SELECT *
  FROM nobel
 WHERE (subject = 'physics' AND yr = 1980)
    OR (subject = 'chemistry' AND yr = 1984);

9. 1980 Excluding Chemistry & Medicine

Query:

SELECT *
  FROM nobel
 WHERE yr = 1980
   AND subject NOT IN ('chemistry', 'medicine');

10. Early Medicine & Late Literature

Query:

SELECT *
  FROM nobel
 WHERE (subject = 'medicine' AND yr < 1910)
    OR (subject = 'literature' AND yr >= 2004);

11. Umlaut Winner — Peter Grünberg

Query:

SELECT *
  FROM nobel
 WHERE winner = 'Peter Grünberg';

12. Apostrophe Winner — Eugene O’Neill

Query:

SELECT *
  FROM nobel
 WHERE winner = 'Eugene O''Neill';

13. Knights of the Realm (Ordered)

Query:

SELECT winner, yr, subject
  FROM nobel
 WHERE winner LIKE 'Sir%'
 ORDER BY yr DESC, winner;

14. Chemistry & Physics Last (1984)

Query:

SELECT winner, subject
  FROM nobel
 WHERE yr = 1984
 ORDER BY subject IN ('physics','chemistry'), subject, winner;
