# Anomaly Detection - DBSCAN

This is a simple algorithm inspired from DBSCAN algorithm but adapted to analyse the data in order, one by one, because the DBSCAN use to randomly select the data.

The datasets used are some Yahoo public datasets which contains the information about Yahoo servers at a given time. For example, during the night, the servers may be less loaded because there could not be active users, but during the day the servers may be very loaded because users could be active.

The main goal is to prevent and identify the anomaly points from systems. 

The algorithm receives three parameters: the dataset that need to be trained, epsilon and minPts. 
The minPts parameter is used in this example with value 1 because there is only one dimension and the algorithm is going from point to point and measure the distance between their values.
The most important parameter is epsilon, because represents the threshold required by the algorithm to create a new cluster or to keep the current one when the algorithm measure the Euclidean distance between two successive points.
There is an online learning because while the algorithm trains the data, he is able to identify which points are anomalies, so it knows how to work with random data.

The most challenging part is to find the optimal value for epsilon. 
For this purpose, it was used half of the entire dataset and used as training data set. 
The training data set is split into anomaly and non-anomaly objects and the Euclidean distance is applied to see their distances.
In the end, epsilon will be calculated with median function which takes as parameters the maximum value from non-anomaly distances and the minimum value from anomaly distances. 

![image](https://user-images.githubusercontent.com/22441947/109378443-45d9ba80-78db-11eb-82fc-3bd138a3d88e.png)

Further work: Look for other ways to find the optimal value for epsilon parameter. (elbow approach, SVM)
