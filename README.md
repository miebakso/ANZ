# ANZ
This projects contains task from the ANZ virtual internship programs.
## Contents

- [Directories](#dir)
- [Instalation](#data)
- [Task 1](#t1)
- [Result 1](#r1)
- [Task 2](#t2)
- [Result 2](#r2)

## <a name="dir"></a>Directories
    .
    ├── data        # folder containing the transaction data
    ├── static      # folder containing the static images used in README
    └── EDA         # folder containing the jupyter notebok for exploratory data analysis (EDA)

## <a name="data"></a>Data

containing 3 months’ worth of transactions for 100 hypothetical customers. It contains purchases, recurring transactions, and salary transactions.

## <a name="t1"></a>Tasks 1

The goal of this project is to find intersting pattern or insight from the data exploratory
- Any data issues?
- What insight gain from the EDA?
- What insight can be gain from the location?
- Create a slide on 3 most interesting findings

## <a name="r1"></a>Result 1

The jupyter notebook is first used to explore and check whether the data have any issues.
The EDA shows that there are some missing values and multiple values exist in one column ex: long-lat, which should be separated.
Although there are missing values, it's a natural occurence based on the investigation. 
Since there is no heavy cleaning or preprocssing needed, I decided to move to Tableau. 

I believe that every tools have it's advantages and disadvantages. If ML, heavy cleaning and preprocessing needed, jupyter notebook would be better. However there are no coplex issues, Tableau would be more advantages for EDA. Tableau has the interactive EDA that makes it better gaining insights on the data.

The result explanation of the finding could be found on `ANZ Virtual Internship EDA.pdf`

![Customer Spending](static/img0.png)

From the image above, larger transaction occrus more during the weekdays. There are some huge transactions occuring in the weekdays.

![alt text](static/img2.png)

The image above shows the location and intensity of the transaction. Darker blue means that the customer had larger average ammount spent, while darker red means otherwise. The Northen Territory shows that it has a customer with the higest average transaction amount.

![alt text](static/img3.png)

The image above, shows the intensity of the transaction counts. A customer on NSW has the higest transaction count.

![alt text](static/img4.png)

The last image shows the location and spread of the merchants. Most of the merchants are located in the high density populated area like Melbourne and Sydney.

More of the results could be found in the PDF.

## <a name="t2"></a>Tasks 2

- Explore correlations between annual salary and various customer attributes
- Build a simple regression model to predict the annual salary
- Build decision tree based

## <a name="r2"></a>Result 2


### Linear Regresion

Since there are no strong correlation, the  simple regression model might not be accurate.

![alt text](static/img5.png)

The scatter plot shows that the salary has the highest correlation with payment. We use a simple linear regression to model the relationship. We split it into train and test so that we can evaluate the model.

![alt text](static/img6.png)

The graph above shows the result of prediction compared to the training data set. The model does not accurately predict the salary of ANZ customer. The prediction (red) is far off from the actual values (blue).

![alt text](static/img7.png)

The result from the test data also shows that the correlation is not really good. The model is also affected by outliers and in the first place there is no strong correlation between the attributes. 

We use mean absolute error (MAE) and root mean squared error (RMSE) to evaluate the model.

Training Performance:  
MAE: 1956.99  
RMSE: 2828.45  

Test Performance:  
MAE: 1559.67  
RMSE: 2052.49   

### Optimization

Although we can optimize the model by removing / capping the outliers. The data is to small and the outliers and actual values. The trend of the data might be different if we have a bigger data set. Even outliers is deal with in this case, the correlation is not too strong that it will give good result.

### Decision Tree

The decision tree model used the following attributes:
- Age
- Gender
- Payment

We used grid search to figure the optimal parameters for the decision tree.

![alt text](static/img8.png)

TRAINING  
- MAE: 1358.83  
- RMSE: 1961.54   

TEST    
- MAE: 1657.30  
- RMSE: 2448.48  

The result does not differ much compared to Linear Regresion. Both models does not predict the target salary really well. Even if outliers and scaling is done, the performance wouldn't be suitable for predicting the correlation because there is no strong correlation between the attributes and salary.

