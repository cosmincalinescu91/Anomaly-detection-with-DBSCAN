# Anomaly-detection-with-DBSCAN

This is an algorithm inspired from DBScan algorithm but adapted analyse the data in order, one by one, because the DBScan starts randomly.

The used datasets are some Yahoo public datasets which contains the information about Yahoo servers at a given time. For example, during the night, servers are less loaded because there might be no users active, but during the day servers might be very loaded because users are active.

The main goal is prevent and identify the anomaly from the systems. 

The algorithm receives three parameters: the dataset that need to be train, epsilon and minPts. 
The minPts is used in this example with 1 as value because there is a single dimension and the algorithm is going from point to point and measure the distance between their values.
The most important parameter is epsilon, because it is the threshold required by the algorithm to create a new cluster or keep the current one when the algorithm measure the Euclidean distance between two successive points.
There is an online learning because when the algorithm trains the data, he is able to identify which points are anomaly, in the same time, so it knows how to work with random data.

The most challenging part is to find the optimal value for epsilon. 
For this purpose, it was used half of the entire dataset and used as training data set. 
The training data set is split into anomaly and non-anomaly objects and the Euclidean distance is applied to see their distances.
In the end, epsilon will be calculated with median function which takes as parameters the maximum value from non-anomaly distances and the minimum value from anomaly distances. 

![image](https://user-images.githubusercontent.com/22441947/109378443-45d9ba80-78db-11eb-82fc-3bd138a3d88e.png)

Further work: Try to find other ways to find the optimal value for epsilon parameter. (elbow, SVM)
