# CDAC_FINAL_PROJECT

 #### Title: 
   Customer Segmentation Analysis: Uncovering Key Insights Using Azure Databricks
 #### Objective:
 This project was aimed at helping the business better understand customer behavior and optimize marketing strategies. By segmenting the customer base, we enabled the company to create targeted campaigns, improving customer engagement and retention.

#### Problem Statement:
In the competitive retail landscape, understanding customer behavior and predicting churn are crucial. Many businesses face challenges in identifying which customers are likely to churn and in segmenting their customer base for targeted marketing efforts. This project addresses these challenges by building a customer segmentation framework and churn prediction model.Our project addressed this by focusing on:
1.Customer Segmentation: Grouping customers based on their Recency, Frequency, and Monetary (RFM) metrics.
2.Churn Prediction: Building models to predict which customers are likely to churn.
3.Marketing Optimization: Using these insights to propose strategies for retaining high-value customers and re-engaging at-risk ones."

#### Tools and Technique:
We used Azure Databricks for its scalability and integration with other Azure services, which helped us efficiently process large datasets. Techniques like K-Means and PCA allowed us to identify natural groupings within the data, which were then visualized to derive actionable insights.

### workflow:
#### Data Preparation and EDA :
We sourced the data from Kaggle, uploaded it to Azure Blob Storage, and processed it in Databricks.

Data Cleaning: Handled missing values, imputed outliers, and ensured data consistency.
EDA: We performed descriptive statistics and created visualizations like histograms, heatmaps, and pair plots to understand the data distribution and relationships. For instance, we observed a strong correlation between Frequency and Monetary, which helped us prioritize features for clustering and prediction.

#### Feature Engineering:
In the project we done first RFM analysis  to understand customer behavior by breaking it down into three key metrics are Recency, Frequency, and Monetary. These metrics enable us to segment customers based on their purchasing habits and spending patterns, which is importatnt for targeted marketing and churn prediction.
In our project, we calculated three key RFM metrics:
•	Recency: We measured how recently each customer made their last purchase by calculating the number of days since their last transaction.
•	Frequency: We counted the number of transactions made by each customer in a given time frame.
•	Monetary: We summed up the total spending for each customer to identify high-value customers.
Additionally, we labeled customers as churned (1) if they hadn’t made a purchase in the last 6 months, and not churned (0) otherwise. These features were importatnt for building an effective churn prediction model.

#### Model Building:
##### Clustering for Customer Segmentation:
In our project, we used K-Means Clustering to segment customers based on their RFM metrics. To determine the optimal number of clusters, we applied the Elbow Method and identified key segments. Since the data was multi-dimensional, we used PCA to reduce it to 2D, allowing us to visualize the clusters.
The segmentation revealed four major customer groups:
1.Champions: Frequent, high-value customers.( These are our most valuable customers who purchase frequently and spend a lot.)
2.Loyal Customers: Regular buyers with consistent spending.( Regular buyers with moderate spending who frequently engage with the business.)
3.Big Spenders: Infrequent but high-value customers.( Customers who make fewer purchases but have a high monetary value.)
4.Hibernating Customers: Customers who hadn’t purchased recently.indicating they might a churn.. 
These insights enabled us to develop targeted marketing strategies, improving customer engagement and retention and also maximize revenue.

•	Business Impact:
These customer segments provided actionable insights:
-We targeted Champions with loyalty programs to retain them.
-Big Spenders were offered exclusive discounts to encourage more frequent purchases.
-For Hibernating Customers, we designed reactivation campaigns to bring them back.

##### Churn Prediction:
In our project, we aimed to predict customer churn. We started with Logistic Regression as a baseline due to its simplicity. Then, we explored more complex models like SVC and Gradient Boosting Classifier. Given the dataset’s imbalance, we applied SMOTE to oversample the minority class, ensuring the model learned patterns for both churned and non-churned customers.

To validate performance, we used K-Fold Cross-Validation and optimized the model through Hyperparameter Tuning. Ultimately, Gradient Boosting gave us the best accuracy of 92%, outperforming other models. This model helped us predict churn effectively, enabling the business to retain high-value customers through targeted interventions..
##### Business Impact:
This model allowed us to:
-Identify high-risk customers early.
-Implement targeted retention strategies, such as personalized offers, which improved customer retention and reduced churn.

#### Model Evaluation:
Once we trained our churn prediction model, the next step was to evaluate its performance using key metrics. This helped us understand how well the model could predict customer churn and identify areas for improvement.
-After evaluating the model, we found:
•	High Recall: 
Our model was effective at identifying most churned customers, which is crucial since missing an at-risk customer could result in lost revenue.
•	Balanced F1-Score: 

This indicated the model maintained a good trade-off between precision and recall, minimizing both false positives and false negatives.
-Insights:
We used the model's predictions to identify which customer segments were at the highest risk of churning. For instance:
•	Hibernating Customers: 
Had high recency and low frequency, meaning they hadn’t engaged recently.
•	Big Spenders at Risk: 
Customers who historically spent a lot but showed declining engagement.
These insights helped us target specific segments with personalized retention strategies, such as offering discounts or loyalty rewards to high-risk, high-value customers.

#### Marketing strategies:
-Based on our customer segmentation and churn predictions, we developed targeted marketing strategies. For Champions, we focused on loyalty rewards and exclusive offers to retain their engagement. 
-For Big Spenders, we used targeted reminders and upselling opportunities. Hibernating Customers were re-engaged through win-back campaigns offering exclusive discounts, while At-Risk Customers received personalized incentives to reduce their likelihood of churning.
-By aligning our strategies with customer behaviors and churn risks, we optimized retention efforts, increased revenue from high-value customers, and reduced churn rates.
-These strategies helped:
•	Retain high-value customers, boosting revenue from loyal segments.
•	Re-engage at-risk customers, reducing churn and improving customer lifetime value.
•	Optimize marketing spend by focusing efforts on the most impactful customer groups.

#### Deployment:
In the deployment phase, we set up Azure Blob Storage to store our data securely and scalably. We then configured an Azure Databricks workspace, where we deployed our churn prediction and customer segmentation models. This allowed us to generate real-time predictions using live customer data.
We also integrated these models with marketing tools like CRM systems, enabling automated, data-driven campaigns. For example, at-risk customers identified by our models would automatically receive re-engagement offers, improving retention rates. This deployment pipeline ensured our insights were actionable, timely, and seamlessly integrated into business operations

#### Insights and Result:
Clustering revealed distinct customer segments:
-Champions: High spending, frequent purchasers.
-Loyal Customers: Regular buyers with moderate spending.
-Big Spenders: High monetary value but less frequent purchases.
-Hibernating: Customers who haven’t purchased recently.
The churn prediction model identified at-risk customers with high accuracy.

#### Challenges :
Data Complexity: High dimensionality and mixed types of features.
Imbalanced Dataset: Resolved using SMOTE.
Model Overfitting: Mitigated through hyperparameter tuning and cross-validation.
Azure Deployment: Required meticulous setup for seamless model integration.

#### Future Scope:
Enhanced Personalization: Use AI to refine customer segments and predict individual behavior.
Real-Time Data Processing: Ingest and process live data streams in Azure Databricks for dynamic segmentation.
Geospatial Analysis: Include location data for regional strategy optimization.
