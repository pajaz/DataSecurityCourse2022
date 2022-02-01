# 0 SELECT basics  

1. SELECT population FROM world  
      WHERE name = 'Germany' 
    Population: 80716000  
2. SELECT name, population FROM world  
      WHERE name IN ('Sweden', 'Norway', 'Denmark');  
    <img src="../../../Pictures/Lesson2/sqlZoo0-2.png">  
3. SELECT name, area FROM world  
      WHERE area BETWEEN 200000 AND 250000  
    <img src="../../../Pictures/Lesson2/sqlZoo0-3.png">