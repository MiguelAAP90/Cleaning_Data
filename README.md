#Cleaning 1000 rows in a meaningful way for analysing.

#It is only to practise the code in SQL and not forget it.
#The data set consists of 1000 lines and 24 columns. a relatively small data but good to keep the practice.



[World_information.csv](https://github.com/MiguelAAP90/Cleaning_Data/files/7849036/World_information.csv)




#the main goal is to understand the data, break the data into different tables in a way that it is easier to read and analyse and after as a second project use those tables to #create visualisations with Tableau.

#after analysing the data I decided to divide the data into 3 different tables City, Country and Language to do so the next code would do the job for each one.

#The data set is called "new_schema" ~this would be different from your pc. Make sure to know the name from your data set and change this name on the code below.





///// City Table--- this code would create this table: 
[World_city.csv](https://github.com/MiguelAAP90/Cleaning_Data/files/7849528/World_city.csv)
 ////

                                        create table City as (select 
                                        ID,
                                        City_name,
                                        CountryCode,
                                        District,
                                        City_Population 
                                        from new_schema.world_information 
                                        group by ID)




//// Country Table--- this code would create this table: 
[World_Country.csv](https://github.com/MiguelAAP90/Cleaning_Data/files/7849531/World_Country.csv)/////

                                        create table Country as (select 
                                        Code, 
                                        Name, 
                                        Continent, 
                                        Region, 
                                        SurfaceArea as Surface_Area, 
                                        IndepYear as Indep_Year, 
                                        Country_population, 
                                        LifeExpectancy as Life_Expectancy,
                                        GNP,
                                        GNPOld as GNP_old,
                                        LocalName as Local_NAme,
                                        GovernmentForm as Government_Form,
                                        HeadOfState As Head_of_State, 
                                        Capital, 
                                        Code2 
                                        from new_schema.world_information 
                                        group by Code)





//// Language Table--- this code would create this table: 
[World_Language.csv](https://github.com/MiguelAAP90/Cleaning_Data/files/7849533/World_Language.csv)   /////

                                        create table Country_Language as (select 
                                        Country_Code,
                                        Language,
                                        IsOfficial as Is_Official,
                                        Percentage
                                        from new_schema.world_information 
                                        order by Country_Code)
                                        
                                        
 
After we finish the cleaning we going to use this data to do couple of visualisations.
https://public.tableau.com/views/Languageandcities/Dashboard1?:language=es-ES&:display_count=n&:origin=viz_share_link
