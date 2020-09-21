# Challenge Data Analysis

- Type of Challenge: `Consolidation`
- Duration: `3 days : Thu,Fri,Mon from 17/09/2020 to 21/09/2020`
- Team challenge : 3
    |  [Michaël](http://https://github.com/mpietquin "Michaël")|[Jean-Christophe](https://github.com/jcmeunier77 "Jean-Christophe") |[Maxime](https://github.com/MDropsy "Maxime") |
    | :------------: | :------------: | :------------: |
    
## Mission objectives 
- Be able to use pandas
- Be able to use Data visualisation libraries.(Matplotlib and/or Seaborn)
- Be able to establish conclusions about a dataset. 
## The Mission
The real estate company "ImmoEliza" wants you to create a machine learning model to predict prices on Belgium's sales.

**Step 1 : Data Cleaning**
    
We had to discuss and analyse datas to see which ones we had to keep and wich ones to remove.
###### There was 3 impractical columns : 

- furnished : as it's only for sales houses and apartments this column was most completely left blank.
- type of sale : we had only notarial sale and already removed the ones selling for an annuity from the scrapping phase.
- surface of the plot land : as we already had surface of the land complete.


##### The previously scrapped datas from Immoweb.be :  
    
##### Before cleaning :

- [csv file](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/Final_dataset_house_apartment.csv") : 50 842 entries
    
    ##### After cleaning :
    
- [cleaned csv file](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/DEF_IMMO.csv "cleaned csv file")  : 42 351 entries

**Step 2 : Data Analysis**

- As "ImmoEliza" wants us to create a machine learning model to predit the price , the Price variable will be our target.
- ##### How many rows and columns ?
    Once the dataset have been cleaned , we had  17 columns left and 42 353 rows
- ##### Percentage of missing values :
    
    We only put the columns where values were missing.
    
| number_of_facades  |  house_area | surface_of_the_land  | garden_area  | terrace_area  | state_of_the_building|construction_year |
| :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | 
| 12.8% Houses and 39.6% Appartments  | 0.3%  |  0.6% Houses |  41.1% | 37%| 24.2% |38.3% |

- ##### Correlation :
    - Houses :
        
        GRAPH HOUSE CORRE
    - Appartments :
        
        GRAPH APPART CORRE
- ##### Qualitative and quantitative variables :
 
    We had X quantitative variables and Y qualitative variables after cleaning. 

**Step 3 : Data Interpretation**
