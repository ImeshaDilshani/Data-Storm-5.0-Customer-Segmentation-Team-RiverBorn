#  Data Driven Approach for KJ Marketing

Our project focuses on developing a data-driven solution for KJ Marketing, a retail company seeking to enhance its understanding of customer segments. By analyzing customer purchasing behavior, we aim to classify customers into distinct segments, enabling KJ Marketing to design more effective marketing strategies.

# Team RiverBorn

Introduce the talented individuals who contributed to this project:
<table align = "center">
    <tbody>
        <tr>
            <td align="center">
                <a href="https://github.com/ImeshaDilshani">
                    <img src="https://avatars.githubusercontent.com/u/93858302?v=4" width="100px;" alt="Imesha Dilshani"/>
                    <br />
                    <sub><b>Imesha Dilshani</b></sub>
                </a>
            </td>
          <td align="center">
                <a href="https://github.com/induwara43">
                    <img src="https://avatars.githubusercontent.com/u/90089540?v=4" width="100px;" alt="Imesha Dilshani"/>
                    <br />
                    <sub><b>Jayawinath Induwara</b></sub>
                </a>
            </td>
          <td align="center">
                <a href="https://github.com/NipuniVithana">
                    <img src="https://avatars.githubusercontent.com/u/99274261?v=4" width="100px;" alt="Imesha Dilshani"/>
                    <br />
                    <sub><b>Nipuni Vithana</b></sub>
                </a>
            </td>
        </tr> 
    </tbody>  
</table> 

## Table of Contents
- Addressing Missing Values, Duplicates, and Outliers
- Feature Selection and Relevance
- Feature Scaling and Normalization
- Encoding Strategies
- Feature Correlations and Inter-Feature Relationships
- Target Variable Interpretation
- Algorithms Considered and Final Choice
- Challenges Faced During Model Training
- Enhancing Marketing Strategies
  
# Addressing Missing Values, Duplicates, and Outliers
## Missing Values
- Analyzed the dataset to identify columns with missing values.
- Converted columns "luxury_sales," "fresh_sales," "dry_sales," and "cluster_catgeory" to numeric types, treating invalid values as NaN.
- Initially dropped rows with missing values to maintain data integrity.
- Imputed missing values in the test data using mean imputation for "luxury_sales," "fresh_sales," and "dry_sales."

## Duplicates
- Utilized the drop_duplicates() function to remove exact duplicate rows from the dataset.
- Inspected the dataset for partial duplicates but found none, ensuring a clean dataset.

## Outliers
- Removed rows with specific "cluster_catgeory" values (e.g., 89.0, 95.0, 98.0, 99.0, 100.0) as potential outliers or erroneous data points.
 
# Feature Selection and Relevance
Selected features: "luxury_sales," "fresh_sales," "dry_sales," "outlet_city," and "cluster_category."

## Rationale
- Sales-related features provide insights into customer purchasing behavior."outlet_city" adds geographic context, accounting for regional preferences and influences.
- Domain knowledge, exploratory data analysis, and correlation analysis supported the relevance of chosen features.

# Feature Scaling and Normalization
Applied Standard Scaling to features "luxury_sales," "fresh_sales," and "dry_sales" using StandardScaler from sklearn.preprocessing.

## Benefits
- Improves model performance by ensuring equal contribution of features to distance calculations.
- Prevents bias caused by features with larger ranges.
- Enhances convergence of optimization algorithms, leading to faster and more efficient training.
- Improves interpretability of model coefficients or feature importance values.

# Encoding Strategies
Applied one-hot encoding to the "outlet_city" feature, creating binary columns for each category (e.g., "outlet_city_Batticaloa").

## Impact
- Transformed categorical data into a format suitable for machine learning algorithms.
- Improved model performance by capturing unique characteristics and preferences associated with each category.
- Enhanced interpretability by providing a clear representation of the categorical variable.
  
# Feature Correlations and Inter-Feature Relationships
Performed one-hot encoding and standard scaling, indirectly impacting correlations and relationships.

## Target Variable
- "cluster_category" or "cluster_catgeory" represents different customer segments.
## Feature Correlations:
- One-hot encoding captures the relationship between "outlet_city" and the target variable.
- Standard scaling ensures proportional contribution of "luxury_sales," "fresh_sales," and "dry_sales" to the analysis.
  
## Inter-Feature Relationships
Binary columns created by one-hot encoding are orthogonal, representing independent relationships.
Numerical features may exhibit underlying relationships, e.g., customers buying more luxury goods may also purchase more fresh items.

# Target Variable Interpretation
The target variable, "cluster_category," defines six distinct customer segments based on purchasing behavior and preferences:

- Cluster 1 ("High-End Shoppers"): Strong preference for luxury items, indicating higher disposable income.
- Cluster 2 ("Fresh Food Enthusiasts"): Focus on fresh produce and perishable goods, indicating health-conscious choices.
- Cluster 3 ("Dry Goods Loyalists"): Reliance on non-perishable dry goods, possibly due to price-consciousness or convenience.
- Cluster 4 ("Balanced Shoppers"): Balanced purchasing behavior across luxury, fresh, and dry goods, indicating versatility.
- Cluster 5 ("Occasional Luxury Buyers"): Occasional indulgence in luxury items, suggesting budgetary constraints or varied spending.
- Cluster 6 ("Value-Conscious Shoppers"): Priority on value for money, with a focus on dry goods and occasional fresh produce purchases.

# Algorithms Considered and Final Choice
Considered algorithms: Logistic Regression, Support Vector Machines (SVM) with OneVsRestClassifier and OneVsOneClassifier.

## Final Choice
- One-vs-Rest (OvR) Logistic Regression: Computational efficiency, simplicity, and fast training times for large datasets.
- One-vs-One (OvO) SVM: Effectively handles complex decision boundaries and high-dimensional feature spaces.

# Challenges Faced During Model Training
- Computational constraints due to large dataset size (700,000 rows).
- Extensive data preprocessing, including feature scaling, handling missing values, and encoding.
- Model evaluation and selection based on multiple metrics.
- Handling outliers during prediction, requiring additional preprocessing steps.
- Increased computational cost due to cross-validation for outlier handling.

# Enhancing Marketing Strategies
Based on the classified clusters, KJ Marketing can implement tailored marketing approaches:

- High-End Indulgence (Cluster 1): Targeted luxury campaigns, exclusive events, and rewards programs.
- Fresh Food Enthusiasts (Cluster 2): Emphasize freshness and quality, provide recipe ideas.
- Dry Goods Loyalists (Cluster 3): Offer bulk discounts and convenience messaging.
- Balanced Buyers (Cluster 4): Personalized recommendations and loyalty programs.
- Occasional Luxury Buyers (Cluster 5): Special occasion promotions and lifestyle branding.
- Value Seekers (Cluster 6): Highlight cost savings and introduce budget-friendly options.
  
# Conclusion
By addressing missing values, duplicates, and outliers, selecting relevant features, applying appropriate scaling and encoding techniques, and interpreting the target variable, we developed a robust customer segmentation model. The chosen algorithms effectively classified customers into distinct segments. Our solution provides KJ Marketing with actionable insights to enhance their marketing strategies, engage different customer segments, and drive sales growth.

This repository showcases our team's data-driven approach, highlighting the power of analytics in understanding customer behavior and improving marketing effectiveness.
