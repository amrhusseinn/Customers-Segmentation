# Customers-Segmentation

The project aims to perform customer segmentation using unsupervised learning methods, specifically K-Means clustering. Customer segmentation helps businesses group customers based on shared characteristics and behaviors, enabling personalized marketing strategies to improve customer loyalty and satisfaction. The dataset consists of customer demographics, including gender and city, which will be used along with additional transactional features to cluster customers into meaningful groups.

The goal is to identify patterns in customer behavior and make recommendations on which customer segments should be targeted for marketing efforts, such as offering coupons to increase retention.

Model Approach
The steps for this project can be broken down as follows:

Feature Selection:
The dataset includes two key demographic features: gender_id and city_id.
These features are chosen for segmentation, with the option to include additional transactional data (e.g., purchase frequency, coupon usage) if available.

Preprocessing:
Numerical features (e.g., city_id) are standardized using StandardScaler.
Categorical features (e.g., gender_id) are transformed into one-hot encoded variables using OneHotEncoder.
These transformations are applied using a ColumnTransformer within a Pipeline to ensure consistency across training and prediction phases

K-Means Clustering:
The K-Means algorithm is applied to cluster customers into groups based on their demographics and potential transactional features.
A range of cluster sizes (from 2 to 10 clusters) is explored, and the optimal number of clusters is determined by evaluating the clustering metrics.
The key evaluation metrics used are Inertia and Silhouette Score.

Model Evaluation:
Inertia: This is the sum of squared distances between each point and the center of its cluster. Lower inertia values indicate more compact clusters.
Silhouette Score: This measures how similar a point is to its own cluster compared to other clusters. A higher silhouette score (closer to 1) indicates well-defined clusters.

Optimal Cluster Selection:
The "elbow method" (using Inertia) and Silhouette scores are used to identify the optimal number of clusters.
The cluster number with the highest silhouette score is chosen as the best solution.

Cluster Assignment and Segment Analysis:
Once the optimal number of clusters is identified, the final model is trained, and each customer is assigned to a specific cluster.
Segment analysis is then conducted to understand the demographics and behaviors of each group.
The analysis includes aggregating features such as gender_id and city_id to understand the average behavior of each segment.
Evaluation Metrics

Inertia:
Inertia is used as a measure of how internally cohesive the clusters are. For each number of clusters, the inertia value decreases as the number of clusters increases. However, beyond a certain point, adding more clusters doesn't significantly improve the inertia value. The elbow in the curve helps determine the optimal cluster size.

Silhouette Score:
The silhouette score provides insight into how well the customers are clustered. Scores closer to 1 mean that customers are well-matched within their clusters and poorly matched to neighboring clusters. A high silhouette score indicates better-defined clusters.
Key Findings

Optimal Number of Clusters:
Based on the elbow method and silhouette score, the optimal number of clusters was identified. In this case, the highest silhouette score corresponds to a cluster count of n (determined by running the code).
Customer Segmentation:

After clustering, each customer is assigned a cluster label. The segments are analyzed to identify key demographic trends. For example, clusters may reveal differences in gender distribution or city preferences.

Business Insights:
The segment analysis can be used to offer targeted marketing strategies. For instance, if one cluster contains a majority of frequent buyers from a particular city, targeted promotions such as coupons can be directed toward that group to increase their loyalty and engagement.

Visualization
Two key visualizations were produced:
Elbow Method Plot: Shows how the Inertia decreases as the number of clusters increases, helping identify the elbow point for the optimal number of clusters.
Silhouette Score Plot: Indicates how well-separated the clusters are for each cluster number, with the highest score indicating the optimal number of clusters.
