**CREDIT**: These commands and original exercise have been adopted from: SQLzoo.net **(https://sqlzoo.net/wiki/SELECT_from_WORLD_Tutorial)**

# First some builtin SQL functions 

## XOR
Exclusive OR (XOR). Show the countries that are big by area (more than 3 million) or big by population (more than 250 million) but not both. Show name, population and area.Australia has a big area but a small population, it should be included.
Indonesia has a big population but a small area, it should be included.
China has a big population and big area, it should be excluded.
United Kingdom has a small population and a small area, it should be excluded.

````
SELECT name, population, area 
FROM world
WHERE (area > 3000000 OR population > 250000000) 
AND NOT (area > 3000000 AND population > 250000000)
````

## LEFT
The capital of Sweden is Stockholm. Both words start with the letter 'S'.
Show the name and the capital where the first letters of each match. Don't include countries where the name and the capital are the same word.
You can use the function LEFT to isolate the first character.
You can use <> as the NOT EQUALS operator.

````
SELECT name, LEFT(name,1), LEFT(capital,1)
FROM world
WHERE (name <> capital) 
AND 
LEFT(name,1) = LEFT(capital,1)
````

