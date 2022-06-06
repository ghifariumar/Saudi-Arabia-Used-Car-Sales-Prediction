# Capstone-Project-3-Saudi-Arabia-Used-Car-Sales

In this project I have to create a Regression Machine Learning model to predict the price of used sales car in Saudi Arabia from syarah.com with dataset from kaggle

## 1. Business Problem

#### Context

Dataset that used is online used car sales in Saudi Arab on syarah.com website. syarah.com is company which offer buying and selling used cars for personal or even for institutional fleets, also offer car auctions. The interaction that occurs in syarahcom is between syarah.com administration and potential buyers without a third party.

Based on [KSA Transportation](https://www.expatarrivals.com/middle-east/saudi-arabia/riyadh/getting-around-riyadh), the main transportation commonly used in Saudi Arabia is personal car because the public transportaion is incovenience especially for tourist who can't speak arabic, the gasoline in Saudi Arabia is not that expensive and the roads in Saudi Arabia are well-maintained. That's make personal transportaion the most suitable choice for people in Saudi Arabia.

Potential buyer who wants to buy a car in syarah.com is pretty easy. User only have to create an account in syarah.com. Then user can choose **New** option for a new car, or **Guaranteed Used** option for used car. Besides that, user also can choose car based on the brand, the shape of the desired model. The car's price is already determined by syarah.com, many factors affect the price of the car. And syarah.com make profit from the difference between the purchasing price syarah.com made and the selling price for potential buyer.

#### Problem Statement

syarah.com's challenge is how to set the suitable price for a car and make profit out of it financially with consindering the condition of the car, and how to set the price that also can compete with other competitors and become costumer priority for buying a car especeially used car in this case.

the consideration syarah.com make to set the car's price is the car's condition, car's production year, the machine, and many more to make the price is competitive and sutiable with the quality of the car.

#### Goals

Based on the issue, syarah.com need a 'tool' that can make a prediction to set a suitable price for them to market the used car. The differences in various features such as years, usage on a used car unit may increase the accuracy of predicting the price. With making this model syarah.com can make a good profit from selling used car

#### Analytic Approach

Analysis needed to be done is analyzing the dataset to create a pattern based on the existence various features, which will differentiate the price of every cars.

Next step needed to be done is to build a regression model which will support the company to set a suitable price for the cars.

#### Metric Evaluation

Metric Evaluation used are RMSE, MAE and MSE. Which RMSE is the mean value of the square root of the error, MAE is the mean absolute value of the error, while MSE is the mean square of the error. The smaller RMSE, MAE, and MAPE values, it means that the model is more accurate in predicting prices according to the limitations of the features used. 

In addtion, we can also use R-squared value. The R-squared value is used to determine how well the model can represent the overall variance of the data. The closer to 1, the more fit the model is to the observation data. However, this metric is not valid for non-linear models.

## 2. Data Understanding

- The dataset is listing data for used car sales from syarah.com in Saudi Arabia.
- Each column represents information related to used car sales listings.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Type | Object | Car Type |
| Region | Object | Location Car Listing |
| Make | Object | Brand |
| Gear_Types | Object | Transmission |
| Origin | Object | Car Origin |
| Options | Object | Used Car Options |
| Year | Integer | Production Year |
| Engine_Size | Float | Engine Size |
| Mileage | Integer | Mileage |
| Negotiable | Boolean | True (if the price is no set) |
| Price | Integer | Car Price |

<br>

## 3. Data Preprocessing

<img width="396" alt="image" src="https://user-images.githubusercontent.com/99155979/169745753-20103675-eb5f-44fe-a459-bad9589ad363.png">
==========================================================================
<img width="397" alt="image" src="https://user-images.githubusercontent.com/99155979/169745789-a9f0b5f0-2cc0-4170-b24a-61d1d8e8512c.png">
==========================================================================
<img width="322" alt="image" src="https://user-images.githubusercontent.com/99155979/169745823-4856ac02-3615-48a7-b245-234aa36a81b2.png">
==========================================================================
<img width="605" alt="image" src="https://user-images.githubusercontent.com/99155979/169745873-42100ab1-d881-47c4-ac7e-8ba212f30e17.png">
==========================================================================
<img width="668" alt="image" src="https://user-images.githubusercontent.com/99155979/169746260-004284b5-54b8-4385-ab20-d9840deda487.png">

```python
- Dropping zero price value. Because it means the price hasn't set yet so it's become irelevant to predict the price.
```

## 4. Modelling

<img width="674" alt="image" src="https://user-images.githubusercontent.com/99155979/169746580-7dace8fa-c3f4-460a-a305-5ad9a4349f9c.png">
==========================================================================
<img width="701" alt="image" src="https://user-images.githubusercontent.com/99155979/169746633-dc1e5527-7c52-4540-8880-04fbfcf2b5a5.png">
==========================================================================
```python
Using 5 Models:
- Linear Regression
- KNN
- Random Forest
- Decision Tree
- XGBoost
```

## 5. Hyper Parameter Tuning

Tuning 2 out of the best from Evaluation Metrics

#### Random Forest

<img width="586" alt="image" src="https://user-images.githubusercontent.com/99155979/169747018-ec54a249-c62d-4e14-afa1-0ff3a7c79ac5.png">

#### XGBoost

<img width="698" alt="image" src="https://user-images.githubusercontent.com/99155979/169747123-05dfd38c-5fd9-4cb2-8b4c-0c8f99e82ef9.png">

## 6. Conclusion

The Evaluation Metrics used in the model are R2, MAE, MSE, RMSE. Based on the value of the Evaluation Metric, the best value is found in the `Random Forest` and `XGBoost` models with the assessment carried out on the RMSE testing number:

| **Evaluation Matrix** | **Random Forest Base** | **XGBoost Base** |
| --- | --- | --- |
| RMSE | 38636.18 | 40063.36 |

Based on these results, Hyperparameter Tuning was then performed on the two models which resulted in the following RMSE results:

| **Evaluation Matrix** | **Random Forest Tuned** | **XGBoost Tuned** |
| --- | --- | --- |
| RMSE | 39906.01 | 37912.42 |

From these results, it is concluded that the XGBoost model is the best model with the lowest RMSE value after Hyperparameter Tuning is performed

These results are not that good because many features are dropped and also the number of iterations when tuning is determined because it is limited and adapted to the device used.

## 7. Recommendation

Things that can be done to develop the model to be even better, such as:

If possible, analyze the features and check the corellation for every features with the target, in this case is the price. In addition, adding and removing of features also affects the results of the model because the more complex it is, the more detailed the model will be. Try using other models that are more complex also affects  the results of the model. However, if the amount of data and features is still like this dataset, it will most likely not change the results significantly.

In addition, try creating Machine Learning models in the form of classification, for example making models to determine whether the car to be sold is profitable or not by determining the price of the car to be sold, the showroom owner also knows the car is profitable or not.
