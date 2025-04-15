A scenario I created "Mr Pilusa just had his first month (July) of electronics sales, but he is old school, so he recorded the data in a book, he need it to be transformed into a SQL database, do EDA to see how the data looks like and see who are his frequent customers, do some machine learning predictions to forecast the upcoming month sales in order to have enough inventory"



1. Setting Up the Database
SQL Database Creation :
A SQLite database (sales.db) is created to store customer, product, and sales data.
Three tables are defined:
Customers: Stores customer details (e.g., name, email, region).
Products: Stores product details (e.g., product name, category, price).
Sales: Tracks sales transactions, linking customers and products via foreign keys.
Data Insertion :
Sample data is inserted into the Customers, Products, and Sales tables using executemany().

2. Data Exploration and Visualization
Data Retrieval :
The data from the SQLite database is loaded into Pandas DataFrames for analysis.
Visualizations :
Sales by Product : A bar chart shows the total units sold for each product.
Revenue by Region : A bar chart displays total revenue generated per region.

3. Exploratory Data Analysis (EDA)
Merging Data :
The Sales, Customers, and Products tables are merged into a single DataFrame for analysis.
Additional features like unit_price, month, and day are calculated.
Key Metrics :
Total revenue, average transaction value, total units sold, top-selling products, and revenue by region are computed and displayed.

4. Sales Forecasting
Time Series Analysis :
Daily sales data is aggregated, and missing dates are filled with zero sales.
Two models are used for forecasting:
ARIMA : Predicts future sales based on past trends.
Prophet : Captures seasonality and trends in the data.
Forecasts for the next 3 days are generated and compared visually.
Performance metrics (MAE, MSE, RMSE) are calculated for both models.

5. Customer Segmentation
Clustering :
Customer features (e.g., total spend, average transaction value, purchase frequency) are extracted and scaled.
K-means clustering is applied to group customers into segments (e.g., high-spending vs. low-spending).
PCA is used to visualize clusters in 2D space.

6. Revenue Prediction
Random Forest Model :
A Random Forest regressor is trained to predict revenue based on features like product_id, customer_id, and quantity.
Feature importance is analyzed to understand which factors drive revenue predictions.
The model's performance is evaluated using metrics like MSE, RMSE, and MAE.
Actual vs. predicted revenue is visualized over time.

7. Market Basket Analysis
Association Rules :
An attempt is made to analyze relationships between products purchased together.
However, since each transaction contains only one product, the analysis is not meaningful and results in an empty output.
9. Saving the Model
The trained Random Forest model is saved to a file (random_forest_revenue_model.pkl) using Python's pickle module for future deployment.
