# **Airbnb Price Prediction Project**

## **Overview**
This project explores Airbnb listing prices in six major U.S. cities: New York City, Los Angeles, San Francisco, Washington DC, Boston, and Chicago. Using the dataset provided on [Kaggle](https://www.kaggle.com/datasets/stevezhenghp/airbnb-price-prediction), the goal is to help prospective Airbnb hosts determine competitive pricing for their properties.

The general approach includes:
- **Data Cleaning**: Removing irrelevant or redundant features and handling missing data.
- **Exploratory Data Analysis (EDA)**:
  - Investigating feature correlations with price.
  - Applying dimensionality reduction (PCA, t-SNE) to uncover patterns in high-dimensional data.
  - Analyzing the relationship between geospatial data (latitude/longitude) and price.
- **Feature Engineering**: Incorporating proximity to landmarks and transport hubs to enhance predictive power.
- **Machine Learning Solution**: Implementing regression and classification models to predict prices and classify listings into price tiers.
- **Results and Insights**: Highlighting key findings and providing actionable recommendations for Airbnb hosts.

---

## **Motivation**
Airbnb prices are highly dynamic and influenced by various factors like location, property type, and amenities. Hosts often struggle to set optimal prices, leading to underperformance or missed opportunities. This project addresses this issue by:
- **Providing insights** into the factors affecting Airbnb prices.
- **Helping hosts** set competitive rates to maximize earnings.
- Utilizing a comprehensive dataset to uncover patterns across multiple cities.

---

## **Data Preparation and Cleaning**
The dataset underwent the following steps for preparation:
1. **Feature Dropping**:
   - Irrelevant or low-impact columns such as `host_has_profile_pic`, `host_since`, and `thumbnail_url` were removed.
   - NLP-related columns (`description`, `name`, `amenities`) were excluded due to dimensionality issues.
   
2. **Feature Engineering**:
   - Consolidated `room_type` and `property_type` to reduce categorical diversity.
   - Calculated `review_duration` from `first_review` and `last_review`.
   
3. **Handling Missing Data**:
   - Missing values in key features were imputed based on averages or other logical defaults.
   
4. **Target Transformation**:
   - The target variable (`price`) was log-transformed to normalize its distribution.

---

## **Exploratory Data Analysis (EDA)**

1. **Feature Correlation Analysis**:
   - **Correlation Calculations with Price**: Revealed strong positive correlations between price and features such as `bedrooms` and `bathrooms`.
   - Highlighted city-specific variations in feature importance.
   
   <img src="images/price_distribution_by_city.png" alt="Price Distribution by City" title="Price Distribution by City" width="800">

2. **Dimensionality Reduction**:
   - **PCA**: Reduced features into components capturing maximum variance, providing insights into data structure.
     - The plot below shows PCA components colored by `price_class`.
   
   <img src="images/pca_plot.png" alt="PCA Plot with Price Class as Hue" title="PCA Plot with Price Class as Hue" width="600">

   - **t-SNE**: Highlighted clusters of listings with similar price classes.
     - The t-SNE plot reveals distinct clusters, particularly for higher price classes.

   <img src="images/tsne_plot.png" alt="t-SNE Plot with Price Class as Hue" title="t-SNE Plot with Price Class as Hue" width="600">

3. **Geospatial Analysis**:
   - Mapped listings across cities, using price class as hue.
   - Identified spatial clustering of high-price listings near central urban areas and landmarks.

   <img src="images/geospatial_map.png" alt="Geospatial Distribution of Listings by Price Class" title="Geospatial Distribution of Listings by Price Class" width="600">

---

## **Feature Engineering**
1. **Landmarks and Transport**:
   - Incorporated proximity to key landmarks (e.g., tourist attractions, parks) and transportation hubs (e.g., subway stations, airports).
   - Measured distances from each listing to the nearest landmark or hub, creating additional features.

2. **Purpose**:
   - Improve model predictions by capturing geospatial factors beyond latitude and longitude.

---

## **Machine Learning Solution**
1. **Models Implemented**:
   - **Linear Regression**: Baseline model for price prediction.
   - **Random Forest Regressor**: Captured non-linear relationships between features and price.
   - **Logistic Regression**: Classified listings into price tiers.

2. **Metrics**:
   - Regression: Root Mean Squared Error (RMSE), Mean Absolute Error (MAE).
   - Classification: Accuracy, Precision, Recall.

---

## **Results and Insights**
1. **Key Findings**:
   - Features such as `bedrooms`, `bathrooms`, and geospatial data significantly impact pricing.
   - Proximity to landmarks and transport hubs adds predictive value to the models.

2. **Model Performance**:
   - Best-performing model: Random Forest Regressor with RMSE = `X` and MAE = `Y` (Fill with actual values).

3. **Recommendations**:
   - Hosts should highlight location advantages (e.g., proximity to landmarks) in their listings.
   - Listings with more bedrooms or bathrooms can command higher prices, especially in high-demand areas.

## **Results and Insights**
(Highlight the results obtained from the analysis or machine learning models, and any data-driven insights or recommendations generated.)

## **Individual Contributions**
- **Member 1: Toh Jun Meng**:  
  - Completed EDA
  - Contributed to github and slides

- **Member 2: Low Kan Yui**:  
  - Completed Feature Engineering: Landmarks
  - Contributed to github and slides

- **Member 3: Natanael Tan Tiong Oon**:  
  - Completed Feature Engineering: Transport
  - Contributed to ML solution
  - Contributed to github and slides

## **References**
(List any external references or resources that were consulted during the project, such as documentation, tutorials, research papers, or datasets.)

## **How to Use this Repository**

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:
   ```bash
   cd <project-directory>
   ```

3. Install dependencies (if applicable):
   ```bash
   pip install -r requirements.txt
   ```

4. Run the analysis or model scripts:
   ```bash
   python script_name.py
   ```

5. If there are Jupyter notebooks:
   Open the notebook and run it:
   ```bash
   jupyter notebook notebook_name.ipynb
   ```

## **For More Information**
- For detailed project requirements, please refer to the [Project Requirements](./proj_req.md).
- For video presentation guidelines, please refer to the [Video Presentation Guidelines](./video_req.md).
