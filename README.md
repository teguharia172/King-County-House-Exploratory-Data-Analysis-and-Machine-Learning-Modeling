# King-County-House-Exploratory-Data-Analysis-and-Machine-Learning-Modeling
Exploratory data analysis on King County house price and regression machine learning modeling  


## Background Information :

Fundamental determinant when it comes to selling houses are the the size of the land and the size house itself.
And If you have ever browse house price's through the internet, chances are you know a thing or two about figuring out the value of a property. If the asking price is too high, the likelihood of the home being sold greatly decreases. On the other hand, if a home you are looking to sell is priced too low, you’ll miss out on potential profits.


To make sure a home is fairly priced, an analysis towards a house should always be performed, before buying or selling. This analysis will compare the values of homes in King County and what are the factors that affecting price of a house in King County to come up with an accurate market price prediction with machine learning modeling. 

## Problem Statement :

Most of people know how to figuring out a value of a house based on the size of the property and and the location of the property itself , however there are many more features that's weight in before figuring out the price of a home.

Figuring out a price of a home are more complicated than just the size and location, acocoring to this website (https://www.thebalance.com/the-worst-home-selling-mistake-1798971) even some professional property agent still having a hard times when it comes to establishing a property value

## Goals :

In this notebook we will do an Exploratory data analysis to figure out what are the factors that's affecting house Price's in King County Washington, after that we will create a machine learning model that will help you predict a house price based on the features.

## Workflow : 
  - Data Cleaning : 
    - Filling a random value of a row with median (0 numbers of bathrooms or bedrooms)
    - Recategorize Data
    - Binning
    
  - Exploratory Data Analysis to answer business question
  
  - Feature Engineering & Selection for machine learning process 
    - Encoding all the object value to int value
    - Checking correlation between dependent and independent variable
    - Feature Selection before model building
  
  - Model Building :
    - Splitting data into training and testing 
    - Creating base model with few machine learning algorithm (Linear Regression, Ridge Regression, Lasso Regression, K Nearest Regressor, Decision Tree, and Random Forest)
    - Check the evaluation matric
    - Do Polynomial degree 2 for linear model regression 
    - Hyperparameter tuning for all the model 
    - Checking eval matrix for tuned model 
    - Chose which model that perform the best when predicting house prices in King County
    
## Business Question : 
  - How is location affecting the prices in King County ? and how should you price your house based on the location 
  - What is the factor that is not affecting the price of a house? 
  - How does your Neighbors house factors affecting your house price ? or vice versa 
  - What is the main factor outside the squarefootage that's driving the price 
  - What machine learning algorithm that work the best when it comes to predicting house prices in King County WA
  
<details>
  <summary><h2> Tl;dr (Summary)</h2></summary>


## Concusion / Summary : 
  - Location in general play a role in defining a house, In this King County case there are few factors of location thats affecting the price 
    1. Houses that is located near the the shore tend to have prices above the median price (450.000 $) of all the house in king county, (please take a look at the html file i have mapped 500 samples of house location  from each price group) 
    2. Before buying / selling a house know your average price of the zipcode first, eventhough this dataset is from 1 County in Washington, a different zipcode could affect the average price of a house
    
  
  - While there are many factors that is affecting the price of a house there is factor that's not affecting the price of a house 
    1. **View is one of the feature that's not affecting house prices**, from our analysis we compared average house prices based on view per price group we found out that there's only small to no effect to price of how good / bad the view of house 
    
    
 - While we couldn't get all the details of the house specification of neighbors house, we foundout that **someone house size is positively correlated with their 15 closest neighbors** this tell that most likely the nieghbors have similar features to the house and vice versa, this tell that your neighbors house price is probably somewhat similar to your house price and vice versa
 
 - From our analysis we found out that outside square footage of a house, and location. **Quality of a house play a major role in determining a house price, what means by quality is the quality of Design and Construction**. We found out that out of **502 high quality houses 501 high quality house are above the median price**, that is a **99.8%**.
  1. **House with high Quality has 3x the average value of house with average quality and almost 7 X the average value of house with low quality**
  
 - **Random Forest with HyperParameter Tuning has the Higest evaluation matrix to predict house prices in King County with the accuracy of 89 %**
 
 
 ## Recommedation :
  - **Before Buying a house know your average price for your zipcode first.** Eventhough all this house dataset are from King County in Washington, from the analysis shows that a your zipcode is one of the feature to establishing a house value
 
 
 - **Quality, Quality, and Quality.** This Analysis shows us that quality of a house play a major role when it comes to figuring out house prices. ( the quality here means the quality of construction), if you ever to sell a home in King county Washington make sure to renovate it first
     - **House with high Quality has 3x the average value of house with average quality and almost 7 X the average value of house with low quality**
     - **501 out of 502 houses with high quality** are priced above the median price of the houses 
     

- **Don't worry about your house view.** The analysis shows that there's no  significance of average price and view per price category, this means that you shouldn't **underprice** your home even if it doesn't have the most beautiful view


- **Near the water, sell it for Higher.** Based on the analysis of folium map, if your house is closer to the water, your house are more likely to be priced above the median value (450.000 $)


- **Increase Your Chances to sell the house by having 3 or 4 bedrooms**
  </details>
  
  <details>
  <summary><h2> Click to see the Full Analysis</h2></summary>

  
  ## Analysis
  
  ### How is location affecting prices in King County
  
  ![image](https://user-images.githubusercontent.com/57277832/97068209-dd5a9400-15ef-11eb-8715-47bcf75c73b6.png)

  this figure shows us that even in 1 county that average house price could be analyze deeper into averaging it per zipcode, and knowing your zipcode average price 1 goodway to get a better understanding of your house prices 
  
  ![image](https://user-images.githubusercontent.com/57277832/97068414-953c7100-15f1-11eb-8d4f-7fa820d4f896.png)

**The picture above is an example of mapping of house price is in King County** please look at the html file for the interactive version of the map

  - **Legends**
    - Houses with **Red icon** is house that's  range from 0 - 250 k
    - Houses with  **light red icon** icon is house that's  range from 250 k - 500 k
    - Houses with  **Orange icon** is house that's  range from 500 k - 750 k
    - Houses with  **Black icon** is house that's  range from 750 k - 1 million
    - Houses with  **Blue icon** is house that's  range from 1 million - 2 million
    - Houses with  **Green icon** is house that's  range from 2 million and above
    
 this mapping showed us that house's that tend to be closer to the water / shore's are more likely to be priced above the median price of King County house ($ 450.000)
 
 
 ### What are the features that'not affecting the price of a house 
 
 ![image](https://user-images.githubusercontent.com/57277832/97068648-c0c05b00-15f3-11eb-93eb-26550fe549ef.png)
 
from the data set we can only found that view has little to no effect to the house price in King County WA, take a look at our graph, we are comparing average price of a home in King county based on their view quality **(0 is being the worst while 4 is the best)**. The house that's in the price group **above 2 million has a slight effect** of price changes based on their view quality, however the higher the view quality doesn't the higher the average price, take a look at the view quality of 0 has a slight higher average price compare to the view quality of 1, same goes to the view quality of 2 and 3 for this price group.

For the rest of the price group view quality does not show any effect at all to the average price


### How does your neighbor house size affecting the price of your house and vice versa



![alt-text-1](https://user-images.githubusercontent.com/57277832/97068906-e2224680-15f5-11eb-8f9e-cefcc1f11e6c.png)               ![alt-text-2](https://user-images.githubusercontent.com/57277832/97068929-1990f300-15f6-11eb-87dc-ef878e945203.png)


The living size and the house lot size are both positively correlated from looking at the linear model graph, **and what does it mean?**

This means that you and you're neighbors house are somewhat similar in sizing and living spaces, while we couldn't compare any more features inside the neighbors house, but we could conclude that your neighbors house price is probably somewhat similar to your house price by comparing the size. and this graph below will tell you that the bigger your neighbors house living space or lot the higher the average price of your home, if we combine both of the analysis we can conclude that **you and your neighbors probably have similar house size and price in King County WA**

![image](https://user-images.githubusercontent.com/57277832/97069098-d899de00-15f7-11eb-8fa4-c59e55bd87b7.png)


### What is the main factor outside the squarefootage that's driving the price

![image](https://user-images.githubusercontent.com/57277832/97069181-9cb34880-15f8-11eb-9de3-05ea97255347.png)


**The general public assumption of house prices is the bigger the square footage of a house or living size of the house means more expensive the house is**, well that's kind of what happened in King County Washington as well. the higher price group tend to have a bigger sqft living and sqft lot of the house, **However**, from our analysis in King County we found out that **Quality** play a big role when it to determining the prices, take a look at the graph below


![image](https://user-images.githubusercontent.com/57277832/97069261-4eeb1000-15f9-11eb-8376-19a9a590268e.png)


 - **Average Quality home are 2X more expensive in average from low quality home**
 - **House with high Quality are 3x more expensive compared to house with average quality and almost 7 X more expensive than the average value of house with low quality**
 
 
### What Machine Learning Algorithm that work the best when it comes to prediction house price in king county washington 

based on this case predicting house price / values is a regression task because we are trying to predict a condition has a continous value, for this regression case i used, 
- Linear Regression
- Ridge Regression 
- Lasso Regression 
- K Nearest Regressor 
- Decision Tree  
- Random Forest

#### Base Model : 
![image](https://user-images.githubusercontent.com/57277832/97069549-47c50180-15fb-11eb-8427-efc164e233b9.png)

If we take a look at the table of the base model, random forest has the highest test score, **However** Random Forest is overfitting there's a major difference from the training and the test set, and same goes to **KNeighbors Regressor, and Decision Tree**.

#### HyperParameter Tuning : 
![image](https://user-images.githubusercontent.com/57277832/97069681-fff2aa00-15fb-11eb-9acc-916157f1d561.png)

After the hyper parameter tuning, there's no overfitting condition on all the algorithms, however hyperparameter tuning doesn't work on Linear Regression, and Ridge Regression in this case because the evaluation matrix of both algorithms doesn't seems to change even after hyperparameter tuning.

**For other algorithms** hyperparameter tuning have a positive effect on the evaluation matrix, reduce the evaluation matrix (bagging) for tree based model and Increase evaluation matrix (Boosting) for other model.

**For this house price prediction in King County Washington Random Forest with hyperparameter tuning has the best result** when it comes to predicting houses in King County WA, please check the notebook machine learning  of prediting house price in king county for more details
</details>
