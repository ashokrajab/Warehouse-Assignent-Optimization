# Warehouse-Assignment-Optimization


Automatically choosing the ideal warehouse to fulfill a given order is one of the key parts in a supply chain process. However, solving this problem might not be as straight forward as selecting the nearest warehouse for a given order. This is because in the real world various external factors might come into play such that the nearest warehouse might not always be the optimal choice. 

This project aims to address this gap by considering the feedback given by the customers for the past orders in order to choose the optimal warehouse to fulfill an order. The idea here being, feedback given by the customers tends to encompass the external factors that played a role in fulfilling the order. 

An Optimization model that uses min-cost flow algorithm suggests an optimal warehouse having distance as the evaluation metric. Feedback is collected for these orders and analysed by a KNN model. Based on the analysis the KNN model infers performance of the warehouses. Now Based on the performance of the warehouses, the evaluation metric(distance) associated with the warehouses, and the forth coming orders is scaled higher or lower. This indirectly encourages or discourages the optimization model in choosing a warehouse for the future orders. 

Taking the feedback of past orders in to consideration we were able to improve the overall feedback average of orders by 16%. This suggests that by taking additional factors such as feedback into account we can effectively automate the assignment of the most optimal warehouse for an order. All the while seeing a substantial increase in customer satisfaction.


![diagram](https://github.com/AshokRaja10/Warehouse-Assignent-Optimization/blob/main/images/solution_architecrure.png?raw=true)

Understanding the data.txt file

|Data    |Description for the data present of each line                     |
|------- | ------------------------------------------------------
|100 100 | Map region: 100 x 100 area on Cartesian coordinate               |
|3       | There are 3 different product types                              |
|2       | There are 2 warehouses                                           |
|0 0     | First warehouse is located at [0,0]                              |
|5 1 0   | It has stock of 5 qty of product_0 and 1 qty of product_1        |
|5 5     | Second warehouse is located at [5,5]                             |
|0 10 2  | It has stock of 10 qty of product_1 and 2 qty items of product_2 |
|3 		 | There are 3 orders                                               |
|1 1 	 | First order to be delivered to [1,1]                             |
|2 		 | First order contains 2 items                                     |
|2 0 	 | 1 qty of product_2 , 1 qty of product_0                          |
|3 3     | Second order to be delivered to [3,3]                            |
|3       | Second order contains 3 items                                    |
|0 0 2   | 2 qty of product_0 , 1 qty of product_2                          |
|56   	 | Third order to be delivered to[5,6]                              |
|1   	 | Third order contains 1 item                                      |
|2   	 | 1 qty of product_2                                               |


**References:**

* [Google OR-Tools Min Cost flow problem](https://developers.google.com/optimization/flow/assignment_min_cost_flow)
* [sklearn.neighbors.KNeighborsRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html#examples-using-sklearn-neighbors-kneighborsregressor)
