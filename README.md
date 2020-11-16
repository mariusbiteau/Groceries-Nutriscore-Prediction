# Groceries-Nutriscore-Prediction
Developed a data cleaning script and trained a model that can predict the Nutriscore of each product of the Database for each product (+1,500,000 products).

#### Data Source
We will use the Open Food Fact dataset.

(https://world.openfoodfacts.org/data).

#### Data Description

This dataset have each product as a data point (1443749 products in total), and for each, we have 181 columns which are separated in five sections :

- General information on the product datasheet: name, date of modification, etc.
- A set of tags: product category, location, origin, etc.
- The ingredients that make up the products and their possible additives.
- Nutritional information: quantity in grams of a nutrient per 100 grams of the product.
- Nutriscore : Also known as the 5-color system, is a nutrition labeling system based on a logo with five values from A to E and from green to red, established according to the nutritional value of a food product. It is implemented by the French government in 2016 as part of the law to modernize the health system.

#### Project Goal

79% of French people are willing to buy a more expensive food product if it contains premium ingredients. (Source: Opinion Way for the National Association of Food Industries (ANIA))

It is not yet mandatory for the manufacturers to display the nutriscore on each grocery product, moreover the dataset being supplied by individuals, the nutriscore is not always noted and the information filled in are often restricted to the barcode and the name of the products and to the nutrients on the back of the package.

Therefore around 50% of the products of the dataset does not have a nutriscore information.

The goal of the project is to understand this dataset, get some insights from it, developp a cleaning algorithm and finally to train a model that can predict the nutriscore for each product in the way of the Yuka application.

![](/nutriscore_examples.jpg)

#### Conclusion 
In this project, we used the Open Food Fact dataset to build a nutriscore grade predictor. 2 different learning classifier (K-NN and Random Forest) were tested, and we have acheived the best prediction performance using Random Forest.

The best prediction performance was acheived using Random Forest regressor, using all features in the dataset and without scaling, and resulted in the following metrics:

- Precision : 0.93
- Recall : 0.93
- F1-score : 0.93

![](/confusion_matrix.png)

![](/Feature_Importances.png)

Finally, we note that after the generalization of our model on all the data (data without nutriscore), the proportion of products with a nutriscore of "A" or "B" slightly decreased and on the other hand the products with a nutriscore of "D" or "E" slightly increased which is explained by the fact that the nutriscore is not yet mandatory; consequently, the companies which have products with a bad nutriscore do not have any marketing interest to show it.

![](/Before_After_Predictions.png)
