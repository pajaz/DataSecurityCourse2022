# 2 SELECT from World  

1.  
  
2. SELECT name FROM world  
      WHERE population >= 200000000  
    <img src="../../../Pictures/Lesson2/sqlZoo2-2.png">  
3. SELECT name, (gdp / population) as 'per capita GDP' FROM world  
      WHERE population >= 200000000  
    <img src="../../../Pictures/Lesson2/sqlZoo2-3.png">   
4. SELECT name, (population / 1000000) as 'pop/mil' FROM world  
      WHERE continent LIKE 'South America'  
    <img src="../../../Pictures/Lesson2/sqlZoo2-4.png">  
5. SELECT name, population FROM world  
      WHERE name IN ('France', 'Germany', 'Italy')  
    <img src="../../../Pictures/Lesson2/sqlZoo2-5.png">  
6. SELECT name FROM world  
      WHERE name LIKE '%United%'  
    <img src="../../../Pictures/Lesson2/sqlZoo2-6.png">  
7. SELECT name, population, area FROM world  
      WHERE area > 3000000 OR population > 250000000  
    <img src="../../../Pictures/Lesson2/sqlZoo2-7.png">  
8. SELECT name, population, area FROM world  
      WHERE area > 3000000 XOR population > 250000000  
    <img src="../../../Pictures/Lesson2/sqlZoo2-8.png">  
9. SELECT name, ROUND(population/1000000, 2) as 'pop/mil', ROUND(gdp/1000000000, 2) as 'gpd/bil' FROM world  
      WHERE continent LIKE 'South America'  
    <img src="../../../Pictures/Lesson2/sqlZoo2-9.png">  
10. SELECT name, ROUND(gdp/population, -3) as 'gdp/pop' FROM world  
      WHERE gdp >= 1000000000000  
    <img src="../../../Pictures/Lesson2/sqlZoo2-10.png">   
11. SELECT name, capital FROM world  
      WHERE LENGTH(name)=LENGTH(capital)  
    <img src="../../../Pictures/Lesson2/sqlZoo2-11.png">  
12. SELECT name, capital FROM world  
      WHERE LEFT(name, 1) = LEFT(capital, 1)  
      AND name <> capital  
    <img src="../../../Pictures/Lesson2/sqlZoo2-12.png">  
13. SELECT name FROM world  
      WHERE name LIKE '%a%'  
        AND name LIKE '%e%'  
        AND name LIKE '%i%'  
        AND name LIKE '%o%'  
        AND name LIKE '%u%'  
        AND name NOT LIKE '% %'  
    <img src="../../../Pictures/Lesson2/sqlZoo2-13.png">  