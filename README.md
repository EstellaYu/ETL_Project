# ETL Project -- Plan on your next advanture abroad! 

## A Data Extract-Transfer-and-Load Porject
| Python | Jupyter Notebook | Pandas | Web scraping | Splinter | SQLAlchemy |   

Members: Elena Castaneda, Brad Daniels, Estella Yu (by last name)

![passport](https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/passport.jpg)

Well, it's summer! It's the time! After a year of hardwork, let's reward yourself with a vacation at your dream place. Suppose you are planning to go for a vacation abroad -- where would you plan for your next advanture? 

Here we have listed several factors that might help you make the wonderful decision! 
1. Considering going aboard -- __`Do I need a visa before I go?`__
2. What are some suggested places from others? -- __`Top 100 desinations worldwide`__
3. What are some advaturous food I can try out? -- __`Popular local dish worldwide`__
4. How does the local economy look like? -- __`Country Population and GDP`__

### Got you excited? Come explore with us!
--------

## EXTRACT 
__Datasets included__
1. [Visa requirement for US citizen](https://en.wikipedia.org/wiki/Visa_requirements_for_United_States_citizens) (`.html`)
2. [Top 100 desitination worldwide](https://brilliantmaps.com/top-100-tourist-destinations/) (`.html`)
3. [World Poluation](https://www.worldometers.info/geography/how-many-countries-are-there-in-the-world/) (`.html`)
4. [Countries GDP data](https://github.com/EstellaYu/ETL_Project/tree/master/GDP_by_country) (`.csv`)
5. [Dish by County](https://github.com/drmonkeyninja/country.json/blob/master/src/country-by-national-dish) (`.json`)

## TRANSFORM 
* __Transform 1: Data Clean-up__

1. __Visa requirement__ for US citizen
   * scrape `html` from Wikipedia website
   * extract table as dataframe
   * unify visa requirement from different description (`Visa not required`, `eVisa/Visa on arrival`, `Visa required`, `Travel restricted`)
   * <img src="https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/visa.png" width = 500>
   
2. __Top 100 desitinations__ worldwide
   * scrape `html` from Wikipedia website
   * extract table as dataframe
   * aggregate dataframe based on countries
   * combine different cities form the same country as a list --> store result in new dataframe
   * <img src="https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/city_list.png" width = 350>
   
3. __Population__ by Country  
`Note: This file has the most complete country list`
    * scrape `html` from website
    * extract table as dataframe  
    * <img src="https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/population.png" width = 400>
   
4. Countries __GDP__ data  
   * load `.csv` files as Pandas dataframe
   * drop unnecessary columns 
   * select the most recent year (2018)
   * dropna
   * <img src="https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/gdp.png" width = 200>
   
5. Yummy Food 
    * Favorite dishese from GitHub Repository `.json`
    * extract table as dataframe
    * <img src="https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/yummy.png" width = 200>

 * __Transform 2: Unify counrty names__
 1. Unify country names from different descriptions, `based on the country name listed by the `__`population`__` dataframe`
 2. Delete records with unnecessary country entries: e.g. listed region instead of country, listed continent data instead of country data, etc. 
 3. Store all dataframes above as `.csv` files
   
## LOAD
  * Create SQLlite Database, and connect to Jupyter notebook with SQLAlchemy
  * Create Entity Relationship Diagram (see below)
    * ![ERD Graph](https://github.com/EstellaYu/ETL_Project/blob/master/resources/database_design.png)
  * Create Python class for each table, Defined column name and type  
  * Load data from dataframe into SQLlite 

 
 
 ## Query Time! 
 Say you decide to go to a country where  
 * you `don't need a visa` to enter, and   
 * try to explore some destineations in the `top 100` list
    
 Here are some cities you might be interested (transformed to pd Dataframe for easier visaulization), and they are ordered based on tourist popularity :) Enjoy your vacation!
 ![query](https://github.com/EstellaYu/ETL_Project/blob/master/resources/Image/query.png)
 

