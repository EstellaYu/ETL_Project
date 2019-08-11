# ETL Project -- Extract, Transfer, and Load


Well, it's summer! It's the time! After a year of hardwork, let's reward yourself with a vacation at your dream place. Suppose you are planning to go for a vacation abroad -- where would you plan for your next advanture? 

Here we have listed several factors that might help you make the wonderful decision! 
1. Considering going aboard -- __`Do I need a visa before I go?`__

## EXTRACT 
__Datasets included__
1. [Countries GDP data](https://github.com/EstellaYu/ETL_Project/tree/master/GDP_by_country) (`.csv`)
2. [Visa requirement for US citizen](https://en.wikipedia.org/wiki/Visa_requirements_for_United_States_citizens) (`.html`)
3. [Top 100 desitination worldwide](https://brilliantmaps.com/top-100-tourist-destinations/) (`.html`)
4. [Dish by County](https://github.com/drmonkeyninja/country.json/blob/master/src/country-by-national-dish) (`.json`)
5. [World Poluation](https://www.worldometers.info/geography/how-many-countries-are-there-in-the-world/) (`.html`)

## TRANSFORM 
* __Data Clean-up__
1. Countries GDP data  
   * load `.csv` files as dataframe
   * drop unnecessary columns 
   * select the most recent year (2018)
   * dropna
   
2. Visa requirement for US citizen
   * scrape `html` from Wikipedia website
   * extract table as dataframe
   * unify visa requirement from different description (`Visa not required`, `eVisa/Visa on arrival`, `Visa required`, `Travel restricted`)
   
3. Top 100 desitination worldwide
   * scrape `html` from Wikipedia website
   * extract table as dataframe
   * aggregate dataframe based on countries
   * combine different cities form the same country as a list --> store result in new dataframe
   
4. Population by Country
    * scrape 'html' from website
    * extract table as dataframe

5. Yummy Food 
    * Favorite dishese from GitHub Repository
    * extract table as dataframe

 Unified by counrty name

* __Store dataframes above as `.csv` files__
   
## LOAD
    * SQLlite create class for each table.   
    * Defined column name and type  
    * Load data from dataframe into SQLlite 
 
 ## ERD graph 
 ![ERD Graph](https://github.com/EstellaYu/ETL_Project/blob/master/resources/database_design.png)

