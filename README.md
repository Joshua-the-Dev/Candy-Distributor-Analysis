# ANALYSING FACTORY-TO-CUSTOMER SHIPMENT FLOWS: A CASE STUDY FROM A U.S. CANDY DISTRIBUTOR

# TABLE OF CONTENT
- CANDY DISTRIBUTOR ANALYSIS - OVERVIEW
- OBJECTIVES OF THE ANALYSIS
- TOOLS USED
- DATA SOURCE
- DESCRIPTION OF RAW DATA
- DATA PREPROCESSING
- EXPLORATORY DATA ANALYSIS (EDA)
- DATA VISUALIZATION
- INSIGHTS
- RECOMMENDATIONS

# CANDY DISTRIBUTOR ANALYSIS - OVERVIEW
This project involves the integration and analysis of sales and geospatial data for a U.S. national candy distributor, with a focus on factory-to-customer shipments. The project aims to uncover insights that can improve distribution efficiency, support strategic planning, and enhance customer service. 

# OBJECTIVES OF THE ANALYSIS
- Identify the most efficient shipping routes from factories to customers.
- Determine the least efficient shipping routes.
- Analyze product lines to find those with the highest profit margins.
- Recommend which product lines should be relocated to different factories to improve shipping efficiency.

# TOOLS USED
- Microsoft Power BI - Data cleaning and preprocessing
- Microsoft Power BI - Data visualization

# DATA SOURCE
The original dataset is gotten from Mavenanalytics.io [DOWNLOAD HERE](https://maven-datasets.s3.amazonaws.com/US+Candy+Distributor/US+Candy+Distributor.zip)

# DESRIPTION OF RAW DATA
The dataset includes the following tables:
- CANDY FACTORIES - Columns in this table are Factory, Latitude, and Longitude.
- CANDY PRODUCTS - Columns in this table are Division, Product Name, Factory, Product ID, Unit Price, and Unit Cost.
- CANDY SALES - Columns in this table are Row ID, Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Country/Region, City, State/Province, Postal Code, Division, Product ID, Product Name, Sales, Units, Gross profit, and Cost.
- CANDY TARGETS - Columns in this table are Division, and Target.
- USZIPS - Columns in this table are Zip, Lat, Lng, City, State_ID, State_Name, Population, Density, Country_Fips, and Country_Name.

# DATA PREPROCESSING
- Data Transformation -
  * Rounded all numerical value columns to two decimal places for consistency.
  * Removed an empty column from the dataset.
  * Eliminated less than 1% of missing values in columns unrelated to the project's objectives.

# EXPLORATORY DATA ANALYSIS (EDA)
- During the EDA phase of the project, key performance indicators (KPIs) were identified and analyzed to better understand the sales data. Highlights include:
  * Total Orders: 8,549
  * Total Sales: $141,783.63
  * Gross Profit: $93,442.80
  * Average Waiting Time: 65.84 months (~5.64 years)

- Order Period: A new column Order_Period was created to calculate the time between the order date and ship date in years:
  Order_Period = DATEDIFF(Candy_Sales[Order Date], Candy_Sales[Ship Date], YEAR)

  Product Margin: A calculated field Product_Margin was introduced to measure profitability as a percentage:
  Product_Margin = ([Total_Gross_Profit] / [Total_Sales]) * 100

  # DATA VIAUALIZAION-
  # INSIGHTS
  # RECOMMENDATIONS
