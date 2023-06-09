![Frame 1](https://github.com/im-hienmai/PJCoffee-POS-data_SQL_PowerBI/assets/131462914/a0e6d3ef-680f-4862-8ad7-462ede6c56c6)

# PJ's Coffee Business Case
INSIGHT AND SUGGESTED SOLUTIONS FROM 2019 SITUATION
<table>
<tr>
<td>
  Clearly define the business objectives of analyzing the POS data, such as evaluating store performance, understanding customer preferences, and identifying opportunities for sales growth and expansion. Align these objectives with the broader goals of PJ's Coffee in Vietnam.
</td>
</tr>
</table>


## Data Used
Data - POS Data with over 100000 rows from two stores of PJ’s Coffee in 2019.

Data Transformation & Cleaning - BigQuery

Data Visualization - PowerBI
## Analysis and Insights
Answer the questions provided and any additional insights gained from the data.
- How sales differed during weekdays and weekends?
- How do sales differ between the two stores?
- How does promotion affect sales?
- What are the favorite products in each store, and are there any differences?
- What recommendations can be made to increase sales for each store?
- Which type of store should PJ's Coffee focus on to expand the market?

## Data Transformation & Cleaning (BigQuery)
The following tables were retrieved using SQL to generate the appropriate data model for conducting analysis and meeting the business needs outlined in the user stories.
### Store1 
    SELECT 
    EXTRACT (DATE FROM Date___Time) as Date,
    EXTRACT (TIME FROM Date___Time) as Time,
    FORMAT_TIMESTAMP ('%A', Date___Time) as Day_of_week, 
    Store,
    Cust_Code, 
    Cust_Name,
    Category,
    Sub_category, 
    Glossary, 
    Account_code, 
    Code, 
    Product_Name, 
    Quantity,
    Unit_Price, 
    Discount_Rate, 
    Discount_Code, 
    Payment_Methods,
    Total_Amount_26 AS Total_sales
    FROM `PortfolioProject.sales_data_store1`
    ORDER BY Date ASC;

### Store2
    SELECT 
    EXTRACT (DATE FROM Date___Time) as Date,
    EXTRACT (TIME FROM Date___Time) as Time,
    FORMAT_TIMESTAMP ('%A', Date___Time) as Day_of_week,
    Store,
    Cust_Code, 
    Cust_Name,
    Category,
    Sub_category, 
    Glossary, 
    Account_code, 
    Code, 
    Product_Name, 
    Quantity,
    Unit_Price, 
    Discount_Rate, 
    Discount_Code, 
    Payment_Methods,
    Total_Amount_26 AS Total_sales
    FROM `PortfolioProject.sales_data_store2`
    ORDER BY Date ASC; 

## Management Dashboard for Sales

### Store 1
<img width="574" alt="store1" src="https://github.com/im-hienmai/PJCoffee-POS-data_SQL_PowerBI/assets/131462914/d9063da3-2655-4eed-9909-649b440d711e">

### Store 2
<img width="572" alt="store2" src="https://github.com/im-hienmai/PJCoffee-POS-data_SQL_PowerBI/assets/131462914/43c61745-044c-46a8-9d61-4057ea6b6f0f">

## Inconlusion

At Store 1, the potential for "Services" is enormous but remains untapped. The service events typically take place from 12:00 PM to 1:00 PM, followed by 4:00 PM.

At Store 2, Saigon Coffee Academy has the potential to increase revenue, as learners mostly visit at 1:00 PM or 3:00 PM.

### Insight 
<table>
<tr>
<td>
Customers show reluctance to actively engage with PJ's Coffee's social media unless prompted to do so, and they are hesitant to try new dishes from a menu that is too diverse.
</td>
</tr>
</table>

### Solutions

1. Streamline the menu by removing unsold or overstocked products. Suggest the menu based on best-selling and must-try items.
2. Increase interaction with PJ's Coffee's social media accounts through check-in or check-in standee programs at the store.
3. Modify combo combinations to include a mix of both best-selling and non-best-selling items to stimulate consumption and boost sales. Consider changing the combination periodically to provide customers with updated options.
4. Incorporate brief information about New Orleans on the packaging to promote the brand. Explore the option of selling PJ's Coffee's traditional coffee in cans or bottles to encourage customers to try it.




