# ETL_Project
ETL Project about Contries Woldwide

## EXTRACT 
__Datasets included__
1. [Countries GDP data](https://github.com/EstellaYu/ETL_Project/tree/master/GDP_by_country) (`.csv`)
2. [Visa requirement for US citizen](https://en.wikipedia.org/wiki/Visa_requirements_for_United_States_citizens) (`.html`)
3. [Top 100 desitination worldwide](https://brilliantmaps.com/top-100-tourist-destinations/) (`.html`)
4. [CIA dataset on contries funfact](https://github.com/iancoleman/cia_world_factbook_api) (`.json`)

## TRANSFORM 
__Data Clean-up__
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
   
4. CIA dataset on contries funfact
   * load `.json` file from API requests
   * flatten `.json` based on counties
   * store result as dataframe
   
__Store dataframes above as `.csv` files__
   
## LOAD

 
