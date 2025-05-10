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
- Data Modelling -
  * Established accurate and efficient relationships between fact and dimension tables to ensure data integrity and enable reliable analysis across all business metrics.

<img width="959" alt="Screenshot 2025-05-10 183452" src="https://github.com/user-attachments/assets/36ffe692-0aaa-4017-9cac-d64abb9c2178" />


# EXPLORATORY DATA ANALYSIS (EDA)
- During the EDA phase of the project, key performance indicators (KPIs) were identified and analyzed to better understand the sales data. Highlights include:
  * Total Orders: 8,549
  * Total Sales: $141,783.63
  * Gross Profit: $93,442.80
  * Average Waiting Time: 65.84 months (~5.64 years)

- Order Period: A new column named Order_Period was created to calculate the time difference between the order date and ship date, measured in years. The Data Analysis Expressions(DAX) formula used is: 
  Order_Period = DATEDIFF(Candy_Sales[Order Date], Candy_Sales[Ship Date], YEAR)

- Product Margin: A new measure named Product_Margin was created to calculate profitability as a percentage. The DAX formula used is:
  Product_Margin = ([Total_Gross_Profit] / [Total_Sales]) * 100

<img width="960" alt="Screenshot 2025-05-10 182845" src="https://github.com/user-attachments/assets/e24c5f73-a84d-4b59-9a19-ee8623ae752d" />


  # DATA VISUALIZAION

<img width="587" alt="Screenshot 2025-05-10 184529" src="https://github.com/user-attachments/assets/1428c466-c483-474c-a226-57f4db7cdc67" />

<img width="588" alt="Screenshot 2025-05-10 184646" src="https://github.com/user-attachments/assets/3a1018a8-2ae3-4e43-a180-2dc295b859f3" />

  # INSIGHTS
The analysis revealed the following key findings:
- Most Efficient Shipping Route:
  * Shipping from the Lot's O' Nuts factory using the Standard Class shipping method proved to be the most effective. This route handled the majority of orders and generated the highest sales overall.
  * The Wicked Choccy factory also demonstrated strong performance when using the Standard Class shipping mode, making it another efficient option.
- Least Efficient Shipping Route:
  * Orders shipped from the Sugar Shack factory via Same Day delivery were the least efficient. This route was the least utilized and resulted in the lowest sales figures.
- Product Line Margins:
  * The Sugar division had the highest product margin at 68.10%, closely followed by the Chocolate division at 67.45%.
- Sales Trends:
  * The United States accounted for the highest sales, totaling $138.83K, significantly outperforming Canada, which recorded $2.95K in sales.
  * Sales consistently increased throughout the year, with December showing the highest sales between 2021 and 2024. Conversely, the beginning of each year typically saw the lowest sales activity.
  
  # RECOMMENDATIONS
  Based on the analysis, the following actions are recommended:
  - Optimize Factory Allocation: Consider relocating the Sugar and Other product divisions to either the Lot's O' Nuts or Wicked Choccy factories to take advantage of more efficient shipping routes and improve overall logistics.
  - Expand Canadian Market Presence: With established shipping routes between the U.S. and Canada, marketing efforts or targeted promotions should be introduced to increase brand awareness and customer engagement in the Canadian market.
  - Boost Early-Year Sales: Implement calculated discounts or promotional campaigns at the beginning of each year to counteract the seasonal dip in sales typically seen during this period.
  - Reduce Order-to-Ship Time: Investigate the causes of the current high average waiting time between order placement and shipping. Operational improvements should be made to streamline this process and enhance customer satisfaction.
  - Review Underperforming Factories: Analyze the low order volumes from the Secret Factory, The Other Factory, and Sugar Shack. Based on findings, either reallocate production to more in-demand products or consider phasing out underutilized facilities to optimize resource use.
