### Purpose of the research
An attempt to predict YC investment size and determine features that influence size of investment the most.
### Method
I use the table with companies information scrapped from YC and table with information about investment deals from root folder. I join them on company name. Then I do some preprocessing to prepare features for linear regression and train the model on the resulting data. Then I look at statistical properties of features to determine ones that have statistical influence.   
Further description of preprocesseing and information about the model can be found in the file `analysis.csv`
### Result
Most statistically significant features are team size, deal date and deal type.