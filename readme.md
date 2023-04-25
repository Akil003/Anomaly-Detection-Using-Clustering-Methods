# Anomaly Detection of Network Packets using UNSW-NB15 Dataset

This project aims to detect anomalous network packets using the UNSW-NB15 dataset available at https://research.unsw.edu.au/projects/unsw-nb15-dataset. Specifically, we use unsupervised learning techniques such as isolation forest and DBSCAN for clustering on the preprocessed data.

## Dataset

The dataset used in this project is specifically `UNSW-NB15_4.csv` which can be found inside the link above. This is a network traffic dataset that contains both normal and attack traffic. It has a total of 49 features, including source and destination IP addresses, port numbers, protocol types, and flow statistics.

Since we are interested in clustering, we have removed the labels from the dataset.

## Preprocessing

Before applying clustering techniques, we have preprocessed the data to prepare it for analysis. The preprocessing steps we performed include:

- **Missing value imputation**: We have removed the rows and columns with a lot of missing values.
- **Feature scaling**: We have scaled the features to have a mean of 0 and variance of 1 using StandardScaler from scikit-learn.
- **PCA**: We have used PCA to reduce the dimensionality of the data.

## Clustering Techniques

We have used two unsupervised learning techniques for clustering:

- **Isolation Forest**: This is an algorithm that detects anomalies by isolating them into individual trees. We used the implementation provided by scikit-learn.
- **DBSCAN**: This is a density-based clustering algorithm that groups together points that are close to each other. We used the implementation provided by scikit-learn.

## Results

We evaluated the performance of both clustering techniques using Visual Inspection. Both of them have identified similar network packet traffic as abnormal network packets. However, DBScan seems to be more adaptable as it not only identifies the outliers but also include different clusters which might give more insight into the type of network or even possibly different types of abnormalities. 

Overall, we were able to successfully detect anomalous network packets using unsupervised learning techniques on the preprocessed data.

## To Reproduce
1. Clone the repository to your local machine.
2. Create a `data` directory in the main directory of the cloned repository.
3. Save `UNSW-NB15_4.csv` from the dataset (available at https://research.unsw.edu.au/projects/unsw-nb15-dataset) in the `data` directory.
4. Run the `preprocessing.ipynb` notebook to preprocess the data.
5. Run the `IsolationForest.ipynb` and `DBScan.ipynb` notebooks to perform anomaly detection using the isolation forest and DBSCAN algorithms, respectively.