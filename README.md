# Data_Cleaning_-_Visualization_using_Matplotlib_-_Seaborn_
This data analysis and data visualization project using the Taxi Dataset handles modern data pipeline workflows, including handling missing values, structural formatting, and an in-depth visual analysis of trip fares, distance correlations, payment structures, and regional trends.

📋 **Table of Contents**
      * Dataset Overview
      * Data Cleaning & Imputation
      * Key Insights & Visualizations
      * Technologies Used

🚕 **Dataset Overview**
    The dataset contains 6,433 trips with 14 relational attributes tracking NYC taxi rides, including:
      * Temporal: Pickup and drop-off timestamps.
      * Financial: Fare, tip, tolls, and total transaction amounts.
      * Geospatial: Pickup/dropoff zones and boroughs (Manhattan, Queens, Brooklyn, Bronx).
      * Categorical: Payment method (credit card, cash) and vendor taxi color.

🛠️ **Data Cleaning & Imputation**
      * Pandas 3.0 Compatibility: Updated structural logic to explicitly include object and string dtypes (df.describe(include=['object', 'string'])) ensuring the codebase is fully backward-compatible and silenced future depreciation warnings.
      * Missing Value Imputation: Missing metrics in categorical fields were handled via mode imputation across localized subsets:
          # python
                df['payment'] = df['payment'].fillna(df['payment'].mode()[0])
                df['pickup_zone'] = df['pickup_zone'].fillna(df['pickup_zone'].mode()[0])
                df['dropoff_zone'] = df['dropoff_zone'].fillna(df['dropoff_zone'].mode()[0])
          # ... extended to pickup and dropoff boroughs
      * Data Health Check: Verified that zero exact logical row duplicates remained via df.duplicated().sum().

📊 **Key Visualizations**
    The Jupyter Notebook features several comprehensive data visualizations generated with matplotlib and seaborn:
        1. Financial Trends Over TimeLine Chart: Tracks fare fluctuations chronologically by converting and sorting tracking points against the pickup datetime axis.
        2. Borough Revenue MetricsBar Chart: Breaks down the total aggregated fares across individual pickup boroughs, pinpointing key economic zones.
        3. Payment Distribution Pie Chart: Visualizes trip distribution across various payment channels (Credit Card, Cash, etc.), highlighting consumer transaction preferences.
        4. Distance Sizing & Metrics Histogram: A granular evaluation of trip ranges restricted to a realistic 0–30 mile index to isolate right-skewed trends while filtering out extreme long-distance outliers.
        5. Multi-Variable Dependencies 
           * Scatter Plot: Maps the exact linear relation of trip distances against transaction fares, colored dynamically by pickup borough.
           * Diverging Correlation Heatmap: An absolute matrix evaluation using the coolwarm palette mapping mathematical coefficients between numerical variables (distance, fare, tip, tolls, total).
        6. Cluster Distributions
           * Pair Plot: A matrix evaluating multi-dimensional pairwise trends filtered specifically across the top 5 busiest pickup zones.
           * Violin Plot: Shows the exact kernel density curvature of fares across distinct categorical payment modes, with internal quartiles clearly identified.
           
💻 **Technologies Used**
      * Python 3.10+
      * Pandas (Engineered for 2.x and 3.x compatibility)
      * NumPy
      * Matplotlib
      * Seaborn
