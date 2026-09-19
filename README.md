# Retail Store Inventory and Demand Forecasting

## 📊 Project Overview

This comprehensive data analytics project focuses on retail store inventory management and demand forecasting using machine learning techniques. The project combines exploratory data analysis, SQL-based business intelligence, and predictive modeling to provide actionable insights for retail inventory optimization.

## 🎯 Business Objectives

- **Demand Prediction**: Develop accurate demand forecasting models to optimize inventory levels
- **Sales Analysis**: Analyze sales patterns across different categories, regions, and time periods
- **Inventory Optimization**: Identify optimal inventory levels to minimize stockouts and overstock situations
- **Seasonal Impact Assessment**: Understand the impact of seasonality, weather, and external factors (epidemics) on retail performance
- **Business Intelligence**: Generate actionable insights for strategic decision-making

## 📁 Project Structure

```
📦 Retail Store Inventory and Demand Forecasting/
├── 📓 Retail Inventory and Demand Forecasting.ipynb    # Main analysis notebook
├── 📄 sales_data.csv                                   # Primary dataset (76,002 records)
├── 📄 SQL_Store_Analysis.sql                          # Comprehensive SQL analysis
├── 📄 README.md                                       # Project documentation
└── 📁 scripts/                                        # Modular SQL analysis scripts
    ├── epidemic_effect_demand_sales.sql               # COVID-19 impact analysis
    ├── inventory_demand_metrics.sql                   # Inventory turnover metrics
    ├── order_fulfillment_metrics.sql                  # Fulfillment rate analysis
    ├── Sales_revenue_metrics.sql                      # Revenue performance metrics
    └── weather_impact.sql                             # Weather & seasonal analysis
```

## 📊 Dataset Overview

### Dataset Specifications

- **Records**: 76,002 retail transactions
- **Time Period**: January 2022 - December 2023
- **Geographic Coverage**: Multi-region retail chain (North, South, East, West)
- **Product Categories**: Electronics, Clothing, Groceries, Toys, Furniture

### Key Features

| Feature              | Description                        | Type        |
| -------------------- | ---------------------------------- | ----------- |
| `Date`               | Transaction date                   | DateTime    |
| `Store_ID`           | Unique store identifier            | Categorical |
| `Product_ID`         | Unique product identifier          | Categorical |
| `Category`           | Product category                   | Categorical |
| `Region`             | Geographic region                  | Categorical |
| `Inventory_Level`    | Current stock level                | Numeric     |
| `Units_Sold`         | Units sold in transaction          | Numeric     |
| `Units_Ordered`      | Units ordered for restocking       | Numeric     |
| `Price`              | Product price                      | Numeric     |
| `Revenue`            | Total transaction revenue          | Numeric     |
| `Discount`           | Discount applied (%)               | Numeric     |
| `Weather`            | Weather condition                  | Categorical |
| `Promotion`          | Promotion active (Yes/No)          | Boolean     |
| `Competitor_Pricing` | Competitor price                   | Numeric     |
| `Seasonality`        | Season (Spring/Summer/Fall/Winter) | Categorical |
| `Epidemic`           | Pandemic period indicator          | Boolean     |
| `Demand`             | Target variable for forecasting    | Numeric     |

## 🔍 Analysis Components

### 1. Exploratory Data Analysis (EDA)

- **Data Quality Assessment**: Missing values, data types, statistical summaries
- **Distribution Analysis**: Feature distributions and correlation patterns
- **Time Series Analysis**: Sales trends, seasonal patterns, and moving averages
- **Regional Performance**: Geographic sales distribution and regional insights
- **Category Analysis**: Product category performance comparison

### 2. Business Intelligence & SQL Analysis

- **Sales & Revenue Metrics**: Total sales, revenue analysis by category/region
- **Inventory Management**: Turnover ratios, stock level optimization
- **Order Fulfillment**: Fulfillment rates and operational efficiency
- **Seasonal Impact**: Weather and seasonal effects on sales performance
- **Epidemic Analysis**: COVID-19 pandemic impact on retail operations

### 3. Predictive Modeling

- **Target Variable**: Demand forecasting
- **Feature Engineering**: Price ranges, discount categories, seasonal indicators
- **Model Comparison**: Multiple algorithms evaluated
- **Performance Metrics**: R² score, Mean Squared Error (MSE)

## 🤖 Machine Learning Models

### Models Evaluated

1. **Random Forest Regressor** (Primary Model)
2. **XGBoost Regressor**
3. **Extra Trees Regressor**
4. **Linear Regression**
5. **Decision Tree Regressor**

### Model Performance

- **Best Model**: XGBoost Regressor
- **R² Score**: 85%+
- **Feature Importance**: Inventory Level, Units Sold, Price, and Competitor Pricing are key predictors

### Key Features for Prediction

1. **Inventory_Level** - Current stock availability
2. **Units_Sold** - Historical sales performance
3. **Price** - Product pricing strategy
4. **Competitor_Pricing** - Market competition factor
5. **Promotion** - Marketing campaign effect
6. **Epidemic** - External disruption impact

## 📈 Key Business Insights

### Sales Performance

- **Top Revenue Category**: Groceries (₹168.9M, 51% of total sales)
- **High-Value Category**: Furniture (Average price: ₹121.51)
- **Volume Leader**: Groceries (3.1M+ units sold)
- **Growth Opportunity**: Electronics (lowest sales volume)

### Regional Analysis

- **Top Performing Region**: North (Highest revenue in sunny weather)
- **Revenue Range**: ₹131K - ₹138K across stores
- **Regional Specialization**: West region excels in furniture sales

### Seasonal & Weather Impact

- **Peak Performance**: Sunny weather drives highest revenues
- **Seasonal Trends**: Winter shows strong performance for certain categories
- **Weather Optimization**: Revenue varies 15-20% based on weather conditions

### Inventory Insights

- **Turnover Leaders**: Groceries (24-33% turnover rate)
- **Optimization Needed**: Electronics and Toys require inventory strategy refinement
- **Fulfillment Rates**: Vary significantly by region and category

### Pandemic Impact

- **Demand Shift**: Notable changes in shopping patterns during epidemic periods
- **Category Resilience**: Groceries maintained strong performance
- **Recovery Patterns**: Clear trends in post-pandemic recovery

## 🚀 Getting Started

### Prerequisites

```python
# Required Libraries
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
xgboost>=1.5.0
```

### Installation & Setup

```bash
# Clone the repository
git clone [repository-url]

# Navigate to project directory
cd "Day 30 Retail Store Inventory and Demand Forecasting"

# Install required packages
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook "Retail Inventory and Demand Forecasting.ipynb"
```

### Database Setup (Optional)

For SQL analysis, load the dataset into your preferred SQL database:

```sql
-- Create database
CREATE DATABASE Sales_Database;

-- Load data
-- Use your preferred method to load sales_data.csv
-- Then execute the provided SQL scripts
```

## 📋 Usage Guide

### 1. Data Analysis Workflow

1. **Data Loading**: Execute initial data loading and inspection cells
2. **EDA Execution**: Run exploratory analysis sections sequentially
3. **Visualization**: Generate comprehensive charts and plots
4. **Modeling**: Train and evaluate predictive models
5. **Insights**: Review business recommendations

### 2. SQL Analysis

Execute SQL scripts in the following order:

1. `Sales_revenue_metrics.sql` - Revenue analysis foundation
2. `inventory_demand_metrics.sql` - Inventory optimization insights
3. `order_fulfillment_metrics.sql` - Operational efficiency metrics
4. `weather_impact.sql` - Environmental factor analysis
5. `epidemic_effect_demand_sales.sql` - External disruption impact

### 3. Model Deployment

```python
# Load the trained model
import joblib
model = joblib.load('demand_forecast_model.pkl')

# Make predictions
predictions = model.predict(new_data)
```

## 📊 Key Performance Indicators (KPIs)

### Financial Metrics

- **Total Revenue**: ₹455M+
- **Average Transaction Value**: Variable by category
- **Revenue Growth Rate**: Tracked monthly/seasonally

### Operational Metrics

- **Inventory Turnover**: 20-35% (category dependent)
- **Fulfillment Rate**: 70-95% (region/category dependent)
- **Stock-out Frequency**: Minimized through predictive modeling

### Predictive Metrics

- **Forecast Accuracy**: 85%+ (R² score)
- **Demand Prediction Error**: <15% MSE
- **Model Reliability**: Cross-validated performance

## 🔮 Business Recommendations

### Short-term Actions (0-3 months)

1. **Inventory Optimization**: Implement demand forecasting for top-selling categories
2. **Weather-based Promotions**: Launch targeted campaigns during optimal weather
3. **Regional Strategy**: Customize inventory mix based on regional preferences
4. **Promotional Timing**: Align discounts with seasonal demand patterns

### Medium-term Strategy (3-12 months)

1. **Category Expansion**: Grow Electronics product range for revenue diversification
2. **Predictive Analytics**: Deploy ML models for automated inventory management
3. **Supply Chain Optimization**: Improve fulfillment rates in underperforming regions
4. **Seasonal Planning**: Develop category-specific seasonal strategies

### Long-term Vision (12+ months)

1. **Advanced Analytics**: Implement real-time demand sensing
2. **Market Expansion**: Leverage insights for new market entry
3. **Customer Segmentation**: Develop personalized inventory strategies
4. **Sustainability**: Optimize inventory to reduce waste and improve margins


