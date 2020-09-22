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
Our steps can be seen in this file : [A._Data_exploration_and_cleaning](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/A._Data_exploration_and_cleaning.ipynb "A._Data_exploration_and_cleaning")
###### There were 3 impractical columns : 

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
    Once the dataset have been cleaned , we had  17 columns left and 42 353 rows.
    We had 11 quantitative variables and 6 qualitative variables left. 

- ##### Qualitative and quantitative variables :
    In the File B  we handeled the transformation of the qualitative variables into quantitatives ones by grouping them and making new ones when it was essential.
    - [B._Creation_of_new_variables](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/B._Creation_of_new_variables.ipynb "B._Creation_of_new_variables")
- ##### [C. Descriptive : sample description](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/C._Descriptive_Sample_description.ipynb "C. Descriptive : sample description")
    After the cleaning phase of the project, the number of missing data ranged from 0 (for ex. For the price/target) to 34,488 (for the garden area variable). 
Number of houses in the data set is 22,500 as compared to 19,852 apartments.
As for the subtype of properties, the count analysis suggested that several cells are extremely reduced. For example, the total number of pavilion and castle is respectively 1 and 7 (which is in fact normal give that these type of properties is extremely unusual.
The vast majority of properties is from the Flemish Region (24,927 as compared to 13,165 for the Walloon region and 4,260 for the Brussels region). 
For the other variables, the better represented categories are the following : 
    - two façades : 15,374 
    - living space between (house_area) between 120 and 180 m² : 11,653 , 
    - two rooms : 14,063
    - no garden : 34,4488
    - no terrace : 16,497
    - no open fire : 40153
    - as new : 12,489

    
- ##### [C. Exploratory analysis of price distribution](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/C.%20Exploratory%20analysis%20of%20price%20distribution.ipynb "C. Exploratory analysis of price distribution")
Graphs and indexes for the whole sample show that the distribution of the dataset’s target (price) has a strong right asymmetry (skewness > 1) and has a strong kurtosis index (kurtosis >1, distribution too peaked). Taken together, these indexes suggest that the target cannot be considered as normally distributed. However, not having normally distributed data is not an issue for the purpose of the current project. 
Beside evaluating normality, skewness and kurtosis provide a useful insight into the target variable. Strong right asymmetry and global peak indeed suggest that a vast majority (peak) of the sample is situated in the left-ended bounded of the distribution. This is furthermore illustrated by the output values of the ‘describe()’ function (i.a. min-max and quartiles values). Indeed the distance between the min and the second quartile (median) yielded at +/- 270.000 while the distance between de second quartile and the max value is much higher (+/- 700,000). This mean that the first 50% of the sample – starting from the min – are situated in a relatively small window values while the second 50% are much more dispersed. 
Similar analyses were conducted separately for the houses and the apartments and show that the apartment subsample – for the target – is more asymmetric and peaked than the houses subsample.
- ##### Percentage of missing values :
    
    We only put the columns where values were missing.
    
| number_of_facades  |  house_area | surface_of_the_land  | garden_area  | terrace_area  | state_of_the_building|construction_year |
| :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | 
| 12.8% Houses and 39.6% Appartments  | 0.3%  |  0.6% Houses |  41.1% | 37%| 24.2% |38.3% |

- ##### Correlation between variables and the price target:
    - You can found the correlation between all variables in this file : [E. Correlation](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/E.%20Correlation%20variables-target%20and%20variables-variables.ipynb "E. Correlation")
    - Houses :
        
    ![](https://raw.githubusercontent.com/MDropsy/Challenge--Data-Analysis/master/Images/graph_corre_house_cleaned.jpg)
    - Appartments :
        
    ![](https://raw.githubusercontent.com/MDropsy/Challenge--Data-Analysis/master/Images/graph_corre_appart_cleaned.jpg)

 

**Step 3 : Data Interpretation**

- ##### [D._Descriptive](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/D._Descriptive_Mean_price_categories.ipynb "D._Descriptive") : mean price by category/variables
    As a corollary of the previous notebook which provides the values and the missing values count analysis for each variable, the purpose of the current section was to calculate the mean values of the target (price) for each category. 
As shown in the [notebook B](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/B._Creation_of_new_variables.ipynb "notebook B"), the continuous variables (mainly surface values) were categorized to allow for means comparisons. For example, the house area continuous variables was transformed into 5 categories : [0-60 m²], ]60-120 m²], ]120-180 m²], ]180-240 m²], ]240m²- ].
Having done this systematically for each considered variables, this provides a useful insight about how the target behave as a function of the other variables. For example, means comparisons for the garden, terrace and open fire variables suggested that the added-value of having a garden or a terrace is about 40,000 euros while the added values of having an open fire is more than 130,000 euros. Although this might seem surprising at a first sight, this suggest that having an open fire goes hand in hand with other luxury features (e.g. spacious house, house of character, mansion).
And here is the exemple graph we obtain for the different provinces :
    
    ![](https://raw.githubusercontent.com/MDropsy/Challenge--Data-Analysis/master/Images/mean_province.PNG?token=AOY7FALPGU3YQWAILC3M2E27NHYRQ)

- #### [F. Regression analyses example](https://github.com/MDropsy/Challenge--Data-Analysis/blob/master/F.%20Regression%20analyses%20example.ipynb "F. Regression analyses example")
    Although, more advanced analyses fell beyond the scope of this project, several scatter plot were graphed along with regression lines (materializing the relationships between two considered variables) differentiated by a third categorical variables. 
For example, the relation between the house area and the price is different for the three considered regions and in particular for the Region Bruxelles-capital where the association area-price is stronger for this region as compared to the two others. ![](https://raw.githubusercontent.com/MDropsy/Challenge--Data-Analysis/master/Images/Regression_price_region.PNG)
Similarly, the relation area-price was seen to be higher for the apartment as for the houses. 

    Finally, a 3D scatter plot was graphed showing the combined relation of the house area and the surface of the land with the houses price. ![](https://raw.githubusercontent.com/MDropsy/Challenge--Data-Analysis/master/Images/3D_regression.png?token=AOY7FAN7775PX5YLFNKXGHS7NHZ2W)
    
Do not hesiste to check each notebook, ask us questions and giving us your tips and tricks ! 
    
    Thank you for your reading , 
    Jean-Christophe, Michaël, Maxime 
