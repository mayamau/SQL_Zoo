# SELECT basics
#### Table: world
|     name    | continent |   area  | population |      gdp     |
|:-----------:|:---------:|:-------:|:----------:|:------------:|
| Afghanistan |    Asia   |  652230 |  25500100  |  20343000000 |
|   Albania   |   Europe  |  28748  |   2831741  |  12960000000 |
|   Algeria   |   Africa  | 2381741 |  37100000  | 188681000000 |
|   Andorra   |   Europe  |   468   |    78115   |  3712000000  |
|    Angola   |   Africa  | 1246700 |  20609294  | 100990000000 |
|     ....    |           |         |            |              |

1.	Show the population of Germany:
```sh
    SELECT population 
    FROM world 
    WHERE name = ‘Germany’;
```

2.	Show the name and the population for 'Sweden', 'Norway' and 'Denmark'.
```sh
    SELECT name, population 
    FROM world 
    WHERE name IN ('Sweden', 'Norway', 'Denmark');
```
3.	Show the country and the area for countries with an area between 200,000 and 250,000:
```sh
    SELECT name, area
    FROM world 
    WHERE area BETWEEN 200000 and 250000;
```

---
