[[Apache Spark]]
**Introduction to Machine Learning:**

- **Definition:** Machine learning is a subfield of computer science that enables computers to learn from data without being explicitly programmed.
- **Origin:** The term "machine learning" was coined by Arthur Samuel in 1959.

**How Machine Learning Works:**

- Instead of defining rules for every possible scenario, machine learning builds models that learn patterns from data.
- For example, in recognizing images of cats and dogs, features like eyes, ears, and tails are analyzed to identify patterns.

**Use Cases of Machine Learning:**

- Machine learning is applied in various fields, such as:
    - **Healthcare:** Diagnosing benign vs. malignant cells using characteristics from a dataset.
    - **Entertainment:** Netflix and Amazon use machine learning for recommendations based on user preferences.
    - **Finance:** Banks use it to assess loan applications by predicting default probabilities.
    - **Telecommunications:** Companies predict customer churn using demographic data.

**Distinction Between AI, Machine Learning, and Deep Learning:**

- **Artificial Intelligence (AI):** A broad field aimed at mimicking human cognitive functions.
- **Machine Learning (ML):** A branch of AI focused on statistical methods to solve problems by learning from examples.
- **Deep Learning:** A specialized area of ML that automates learning and decision-making processes.

**Categories of Machine Learning:** 
![[Supervised_vs_Unsupervised.png]]
**Branches of Machine Learning:**

- **Deep Learning:** Algorithms inspired by the human brain.
- **Natural Language Processing:** Understanding human language.
- **Computer Vision:** Interpreting digital images.
- **Reinforcement Learning:** Learning through rewards and punishments.
---
# Role of Data Engineer in Machine Learning
[[Requirement to be a data engineer]] [[Apache Spark]] [[ETL]]
- **Definition of Data Engineering**: Data engineering is crucial in machine learning, focusing on designing, constructing, and managing the infrastructure needed for data storage, processing, and analysis.
    
- **Responsibilities of Data Engineers**:
    
    - **Data Availability**: Ensuring comprehensive, precise, and relevant data is available for machine learning projects.
    - **Data Collection Process**:
        - Establishing data requirements (types and sources).
        - Identifying specific data sources (databases, APIs, etc.).
        - Collecting data using techniques like querying and web scraping. Ensuring the consistency and structure of the d
- **Data Preparation**:
    
    - **Data Exploration**: Identifying anomalies such as missing values and outliers.
    - **Data Cleaning**: Correcting or removing errors, eliminating duplicates, and addressing inconsistencies.
    - **Data Transformation**: Formatting data for analysis, including normalization and feature selection.
    - **Data Integration**: Combining data from various sources into a unified dataset.
    - **Data Formatting**: Ensuring data is in appropriate formats for analysis.
- **Data Storage Solutions**:
    
    - **Storing Data**: Selecting suitable storage types based on data characteristics.
    - **Organizing Data**: Designing schemas and indexing for efficient data retrieval.
    - **Securing Data**: Implementing security measures to protect sensitive information.
    - **Retrieving Data**: Optimizing data retrieval performance.
    - **Backing Up Data**: Establishing regular backup processes to prevent data loss.
- **Data Transformation and Feature Extraction**:
    
    - **Feature Selection**: Identifying relevant features for analysis.
    - **Scaling Features**: Ensuring comparability among features.
    - **Creating New Features**: Deriving additional features to capture patterns.
    - **Dimensionality Reduction**: Reducing the number of features while preserving essential information.
    - **Encoding Categorical Features**: Converting categorical data into numerical formats.
    - **Handling Missing Values**: Imputing missing data to ensure completeness.
---
# Machine Learning Term
## Regression
- **Definition of Regression**: Regression is the relationship between a **dependent variable** (continuous) and an **independent variable**. It allows for predictions based on existing data.
    
- **Scatter Plot Example**: A scatter plot is used to visualize the relationship between midterm and final grades. For instance, if a student scores 35 on the midterm, their final score can be estimated to be around 40. For a midterm score of 80, the actual final score is 86.5, demonstrating how regression can help make educated guesses.
    ![[RegressionExample.png]]
- **Line of Best Fit**: This line represents the best approximation of the relationship between the variables. The formula for this line is **y = mx + b**, where:
    
    - **m** is the slope (rise over run).
    - **b** is the y-intercept (value of y when x is 0).
- **Calculating the Slope (m)**: For example, if the rise is 76 - 55 and the run is 70 - 50, the slope (m) is calculated as 1.05, indicating that for every 1 mark increase in the midterm, the final score increases by 1.05.
    
- **Y-Intercept (b)**: In this case, the y-intercept is 2.5, meaning a student scoring 0 on the midterm would still score 2.5 on the final.
    
- **Types of Regression**:
    
    - **Linear Regression**: Assumes a linear relationship between variables.
    - **Multiple Regression**: Involves multiple independent variables (e.g., midterm score and attendance).
    - **Polynomial Regression**: Used for non-linear relationships.
    - **Regularized Regression**: Techniques like Ridge (L2), Lasso (L1), and ElasticNet help prevent overfitting by adding penalties to the model.
    
- **Advanced Regression Techniques**:
![[RegressionTechniques.png]]
- **Classification vs. Regression**:
    ![[ClassificationVsRegression.png]]
# Classification
- **Classification Overview**:
    
    - Classification is a type of prediction problem in machine learning that answers the question, “What category does this fall into?”
    - It contrasts with regression, which predicts continuous outcomes.
- **Input Variables**:
    - These are independent variables or features used to make predictions. For instance, factors like "Average score on previous biology tests" or "Number of hours studied" can influence the outcome.
- **Types of Classification**:
    
    - **Binary Classification**: Involves two classes (e.g., pass or fail).
    - **Multiclass Classification**: Involves three or more classes (e.g., predicting handwritten digits or types of fruit).
- **Key Terminologies**:
    
    - **Classifier**: A machine learning algorithm used to solve classification problems.
    - **Feature**: An independent variable used as input in the model.
    - **Evaluation**: The process of validating how well a model has performed.
- **Classification Algorithms**:
	- Two Types of Algorithms: 
    ![[Pasted image 20250226221321.png]]
    ![[Pasted image 20250226221333.png]]
- **K-Nearest Neighbors (KNN)**: This algorithm classifies unknown data points by finding the most common classes among the k-nearest examples.
- **Logistic Regression**: Used to predict the probability of a class based on input features.
- **Decision Trees**: These algorithms use "If-then" rules to classify outcomes.
## Evaluation
Detail : [[Evaluate.pdf]]
1. **Train/Test Split**:
    - It's crucial to split your dataset into a **training set** (to train the model) and a **test set** (to evaluate the model's performance).
2. **Accuracy**:
    - Accuracy is calculated by dividing the number of correct predictions by the total number of observations
    - $$ \frac{True Negative + True Positive}{False Positive + True Positive + True Negative + False Negative}$$
3. **Confusion Matrix**:
    
    - A confusion matrix is a table that compares predicted values against actual values, helping to measure the performance of a classification model. It includes:
        ![[Pasted image 20250226224330.png]]
4. **Precision**:
    
    - Precision is the ratio of true positives to the total predicted positives. 
    - $$ \frac{True Positive}{False Positive + True Positive}$$
5. **Recall**:
    
    - Recall measures the ratio of true positives to the total actual positives. It is crucial in situations where missing a positive case (false negative) has significant consequences, such as in medical diagnoses.
    -  $$ \frac{True Positive}{False Negative + True Positive}$$
6. **F1-Score**:
    
    - The F1-score is the harmonic mean of precision and recall, providing a balance between the two metrics when both are important.
    -  $$ \frac{2 \times Recall \times Precision}{Recall + Precision}$$
7. **Regression Model Evaluation**:
    
    - For regression models, several metrics are used:
        - **Mean Squared Error (MSE)**: The average of the squared differences between predicted and actual values. Lower MSE indicates better model performance.
        - $$ \sum_{i=1}^{n}\frac{(y_{predict} - y_{value})^2}{n} $$
        - **Root Mean Squared Error (RMSE)**: The square root of MSE, providing error in the same units as the target variable.
        $$ \sqrt{\sum_{i=1}^{n}\frac{(y_{predict} - y_{value})^2}{n}} $$
        - **Mean Absolute Error (MAE)**: The average of the absolute errors.
        - **R-squared**: Represents the proportion of variance in the dependent variable explained by the independent variable, with values ranging from 0 (poor fit) to 1 (perfect fit).
## Clustering
- **Definition of Clustering**: Clustering is the process of grouping unlabeled examples in machine learning to identify patterns or connections in data. It uses unsupervised machine learning techniques to form clusters of data points that share similar properties.
    
- **Applications of Clustering**:
    
    - **Customer Segmentation**: Businesses use clustering to categorize customers based on purchase history and demographics, allowing for personalized services.
    - **Image Segmentation**: This involves dividing images into categories based on color and content, which is useful in image analysis and computer vision.
    - **Anomaly Detection**: Clustering helps identify unusual data points that do not fit established clusters, aiding in fraud detection and cybersecurity.
    - **Document Clustering**: This groups similar documents based on content and keywords, facilitating information retrieval and organization.
    - **Recommendation Systems**: Clustering is used to group similar items or products based on customer behavior, enhancing product recommendations in e-commerce.
- **Types of Clustering**:
    
    - **Partitioning Clustering**: Divides the dataset into a specified number of clusters (k), with algorithms like k-means and k-medoids.
    - **Hierarchical Clustering**: Organizes data into a hierarchy of clusters, with algorithms such as agglomerative and divisive clustering.
    - **Density-Based Clustering**: Defines clusters as dense regions of data points separated by lower density areas, with algorithms like DBSCAN and OPTICS.