# Bridge-data-analysis

## Table of contents:
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Methods](#methods)
- [Results](#results)
- [Conclusions](#conclusion)
- [How to Use](#how-to-use)


## Project overview:
This projects investigates factors influencing the condition of bridges in Texas using data from the US National Bridge Inspection (FHWA).
The analysis focuses on five main predictors:
1) Age of the bridge
2)Average daily traffic
3) Percentage of truck traffic
4) Material
5) Design
The target is the current condition of the bridge, derived from deck, superstructure, and substructure ratings.

## Dataset
The dataset (`tx19_bridges_sample.csv`) used in the analysis comes from the US National Bridge Inspection maintained by the Federal Highways Agency (FHWA), part of the US Department of Transportation. The original data comes from the National Bridge Inspection section of the FHWA's web site. The data is about bridges in the US State of Texas! 

## Methods:
1) Data Preparation:
   
- Loaded and cleaned ~34,000 bridge records.

- Removed null/unknown ratings.

- Created an Age variable from the construction year.

- Reduced small categories for Material and Design.

- Excluded historic/very old bridges (treated differently in maintenance).

- Combined ratings into a single condition score.
  

2) Exploratory Data Analysis (EDA)
   
- Distribution plots of numeric variables (Age, Traffic, Trucks%).

- Correlation analysis between numeric predictors.

- Explored how categorical variables (Material, Design, Historic) relate to condition.

- Relationships between categorical variables.
  

3) Regression Analysis
   
- Dummy encoding of categorical variables.

- Linear regression model to predict condition.

- Examined coefficients to identify influential factors.

- Residual analysis to check model assumptions.

## Results
Figure 4:

<img width="687" height="391" alt="Unknown" src="https://github.com/user-attachments/assets/9d1e5758-8c7f-4f81-92c9-507fdbafa4d1" />

Firgure 4: this is a scatter plot with a regression line showing the relationship between bridge age and the conditon scores. In this graph as 'Age' increases, the 'Condition_Scores' decreaces as the regression shows a downwards slope. This suggests that older bridges have poorer conditions. This is a key finding for the Texas Department of Transportation as it shows that age is a significant predictor of bridge deterioration. Therefore older bridges need more inspection.

Figure 5:

<img width="687" height="391" alt="Unknown-1" src="https://github.com/user-attachments/assets/b9b6cee7-32e2-4e5b-aefb-051a0c9451de" />

Figure 5: this shows a scatter plot illustrating the relationship between 'Average Daily Use' and 'Condition Scores. The minimal slope of the regression line suggests that the number of vehicles crossing the bridge daily have little influence on the bridges conditon. This is important as the Texas Department of Transportation can conclude from this gragh that the traffic volume is not a key factor. This also shows that other variables need to be investigated further and resources can be allocated to other predictors as daily use does not contribute highly to the bridges deterioration.

Figure 7:

<img width="687" height="391" alt="Unknown-2" src="https://github.com/user-attachments/assets/6956e66f-b8a6-4efa-8699-c36a7ba4c198" />

Figure 7: this is a bar chart showing the average condtiton scores for bridges made from different materials. Overall the materials used on the gragh do not contribute negatively to the conditon scores. However 'Concrete' bridges generally have higher condtiton scores than those made from 'Timber'. This shows that concrete materials have higher durability and shows the Texas Deprtment that they should invest less in 'Timber' materials in the future.

R2 : 0.360108. This represents the Coefficient of Determination.

R2 - which is the coeffictient of determination vlaues, represents the proportion of variance in the condition score shown by this model. An R2 = 0.36(2dp) shows that 36.01 of the variability in the bridge condition scores can be explained by the proposed predictors. The remaning 63.99% is due to factos not included in this model. Therefore other predictor variables that have not been mentioned have more effcects and should be investigated.

## Conclusion:
Based on the scaled influence, the Coefficent of Determination value (R2), the relationship between the continous and categorical variables, age distibution anlysis and rating map scores i can conclude that'Age' has the hgihest affect on the bridges condition score. It is also the primary driver of the bridge condition, therefore i would advise the Texas Department of Transportation to focus and invest in this variable the most. Such as exploring non-linear models as it may capture any complex relationships between age and bridge conditions. And focus less on the designs of the bridge as that had the least affect based on the R2 values and their condition scores. More importanlty as already stated there are more variables outside of those investigated to be looked into as they account for 63.99% of the predictive power of the model

## How to use:
- Open the Jupyter Notebook file `Bridges-data-analysis.ipynb' to view the full analysis.  
- Run the notebook cells in order to reproduce the data preparation, exploratory analysis, regression modelling, and results.  
- The dataset (`tx19_bridges_sample.csv`) should be placed in the same directory as the notebook. This dataset can be found in the files section of this repository.
