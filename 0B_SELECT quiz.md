# SELECT Quiz
#### Table: world
| name        | region      | area    | population | gdp         |
|-------------|-------------|---------|------------|-------------|
| Afghanistan | South Asia  | 652225  | 26000000   |             |
| Albania     | Europe      | 28728   | 3200000    | 6656000000  |
| Algeria     | Middle East | 2400000 | 32900000   | 75012000000 |
| Andorra     | Europe      | 468     | 64000      |             |
| ...         |             |         |            |             |

1.  Show the countries and their population for countries with a population between 1,000,000 and 1,250,000:
```sh
  SELECT name, population
  FROM world
  WHERE population BETWEEN 1000000 AND 1250000;
```
2.  Show the countries that end in A or L:
```sh
    SELECT name 
    FROM world
    WHERE name LIKE '%a' OR name LIKE '%L';
```
3.  Show the countries that start with AL:
```sh
    SELECT name 
    FROM world
    WHERE name LIKE 'Al%';
```
4.  Show the European countries whose names are 5 characters long:
```sh
    SELECT name, LENGTH(name) 
    FROM world 
    WHERE LENGTH(name) = 5 AND continent = 'Europe';
```
5.	Show the 2x area of the countries whose population is 64000:
```sh
    SELECT name, area *2 
    FROM world 
    WHERE population = 64000;
```
6.	Show the countries with an area larger than 50000 and a population smaller than 10000000:
```sh
    SELECT name, area, population 
    FROM world 
    WHERE area > 50000 AND population < 10000000;
```
7.	Show the code that shows the population density of China, Australia, Nigeria and France:
```sh
  SELECT name, population/area 
  FROM world 
  WHERE name IN (‘China’, ‘Australia’, ‘Nigeria’, ‘France’);
```



---
