# SELECT from Nobel Tutorial


#### Table Name: nobel

| yr   | subject    | winner                      |   |   |
|------|------------|-----------------------------|---|---|
| 1960 | Chemistry  | Willard F. Libby            |   |   |
| 1960 | Literature | Saint-John Perse            |   |   |
| 1960 | Medicine   | Sir Frank Macfarlane Burnet |   |   |
| 1960 | Medicine   | Peter Medawar               |   |   |
| 1960 | Physics    | Donald A. Glaser            |   |   |
| 1960 | Peace      | Albert Lutuli               |   |   |
| ...  |            |                             |   |   |


## Questions:

1.	Show the name of winner's names beginning with C and ending in n:
```sh
  SELECT name FROM nobel
  WHERE winner LIKE 'C%' AND winner LIKE '%n';
```
2.	Show how many Chemistry awards were given between 1950 and 1960:
```sh
  SELECT subject FROM nobel
  WHERE subject = 'Chemistry'
  AND yr BETWEEN 1950 and 1960;
```
3.	Show the amount of years where no Medicine awards were given:
```sh
  SELECT COUNT(DISTINCT yr) FROM nobel
  WHERE yr NOT IN (SELECT DISTINCT yr FROM nobel WHERE subject = 'Medicine');
```
4.	Show subject and name of knighted winners in the 1960s:
```sh
  SELECT subject, winner 
  FROM nobel WHERE winner 
  LIKE 'Sir%' AND yr LIKE '196%';
```
5.	Show the year when neither a Physics or Chemistry award was given:
```sh
  SELECT yr FROM nobel
  WHERE yr NOT IN ( SELECT yr 
                    FROM nobel 
                    WHERE subject IN ('Chemistry','Physics'));
```
6.	Show the the years when a Medicine award was given but no Peace or Literature award was:
```sh
SELECT DISTINCT yr
FROM nobel
WHERE subject='Medicine' AND yr NOT IN( SELECT yr 
                                        FROM nobel 
                                        WHERE subject='Literature')
                         AND yr NOT IN (SELECT yr
                                        FROM nobel 
                                        WHERE subject='Peace');
```
7.	Show the number of awards given per subject in the year 1960:
```sh
  SELECT subject, COUNT(subject) 
  FROM nobel 
  WHERE yr ='1960' 
  GROUP BY subject;
  ```

---
