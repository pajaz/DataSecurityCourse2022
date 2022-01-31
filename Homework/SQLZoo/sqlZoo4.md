# 4 SELECT within SELECT Tutorial

1. SELECT name FROM world  
      WHERE population >   
        (SELECT population FROM world  
          WHERE name='Russia')  
  
2. SELECT name FROM world  
      WHERE (gdp/population) >  
        (SELECT gdp/population FROM world  
          WHERE name LIKE 'United Kingdom')  
          AND continent LIKE 'Europe'  
  
3. SELECT name, continent FROM world  
      WHERE continent IN  
        (SELECT continent FROM world  
          WHERE name IN ('Argentina', 'Australia'))  
      ORDER BY name  
  
4. SELECT name, population FROM world  
      WHERE population BETWEEN  
        (SELECT population+1 FROM world  
          WHERE name LIKE 'Canada') AND  
        (SELECT population-1 FROM world  
          WHERE name LIKE 'Poland')  
        
    * BETWEEN is inclusive so I worked around it by adding one person to the floor (Canada) and removing one from the ceiling (Poland). I could have used the larger than and smaller than operators or excluding Canada and Poland from he results but my solution requires less typing and works for  this particular case.  
  
5. SELECT name as 'Name',  
      CONCAT(  
        ROUND(  
          population/(  
            SELECT population FROM world  
              WHERE name='Germany'  
          )*100,0  
        ), '%'  
      ) as Percentage FROM world  
      WHERE continent LIKE 'Europe'  
  
6. SELECT name FROM world  
      WHERE gdp >   
        (SELECT MAX(gdp) FROM world   
          WHERE continent LIKE 'Europe')  
  
    Another options with the ALL operator which requires a bit more typing:    
    SELECT name FROM world  
      WHERE gdp > ALL  
        (SELECT MAX(gdp) FROM world   
          WHERE continent LIKE 'Europe'  
            AND gdp > 0)  
  
7. SELECT continent, name, area FROM world x  
      WHERE area >= ALL  
        (SELECT area FROM world y  
          WHERE y.continent=x.continent  
            AND area>0)  
  
8. SELECT continent, name FROM world x  
      WHERE name <= ALL   
        (SELECT name FROM world y   
          WHERE y.continent = x.continent)  
  
9. SELECT name, continent, population FROM world x  
      WHERE 25000000 > ALL  
        (SELECT population FROM world y  
          WHERE x.continent = y.continent  
            AND population > 0)  
  
10. SELECT name, continent FROM world x   
      WHERE population = ALL  
        (SELECT population FROM world y  
          WHERE y.continent = x.continent  
            AND y.population*3 > x.population)  