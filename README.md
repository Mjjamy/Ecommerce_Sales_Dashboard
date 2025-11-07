# Ecommerce Sales Analysis

### Project Overview
---

Developed an interactive E-commerce Sales Dashboard in Power BI using time-intelligence functions, advanced formatting, and dynamic visuals to analyze YTD performance, category trends, and regional sales. Insights revealed profit growth despite a drop in overall sales and quantity.

### Data Sources
The primary dataset used for this analysis is the "ecommerce_data_excel.xlsx" which contains information about the sales made by the company.

### Tools

- Microsoft Power BI (Data Cleaning, Data Analysis, Creating Reports)

### Data Cleaning/Data Preparation
- Removed duplicates. 

- Handled missing values.

- Standardized data formats for dates, currency, and categories.

- Validated data types for numerical and categorical fields.

- Filtered irrelevant records to focus on meaningful sales insights.

- Corrected spelling and formatting errors.

- Created calculated columns.

- Renamed columns with clear, readable titles for better understanding.

### Exploratory Data Analysis

EDA was done to uncover insights and answer to key questions such as:

- How do sales and profit vary across regions and states?

- Which product categories and sub-categories generate the highest sales and profit?

- What are the monthly and yearly sales trends (YTD vs PYTD)?

- Which customer segments contribute most to total revenue and profit?

- Which shipping modes are most preferred by customers?

### Data Analysis

Worked with some DAX Queries such as:
```

- Calendar = CALENDAR(MIN(ecommerce_data[order_date]),max(ecommerce_data[order_date]))
- Month = FORMAT('Calendar'[Date],"mmmm")
- Month Number = Month('Calendar'[Date])
- Year = YEAR('Calendar'[Date])
- Profit Margin = SUM(ecommerce_data[profit_per_order])/SUM(ecommerce_data[sales_per_order])
- YTD Sales = TOTALYTD(SUM(ecommerce_data[sales_per_order]),'Calendar'[Date])
- YTD Quantity = TOTALYTD(SUM(ecommerce_data[order_quantity]),'Calendar'[Date])
- YTD Profit Margin = TOTALYTD([Profit Margin],'Calendar'[Date])
- YTD Profit = TOTALYTD(SUM(ecommerce_data[profit_per_order]),'Calendar'[Date])
- YTD Concatenated Quantity = CONCATENATE("#",FORMAT([YTD Quantity]/1000,"0.0K"))
- YOY Sales = ([YTD Sales]-[PYTD Sales]) /[PYTD Sales]
- YOY Quantity = ([YTD Quantity]-[PYTD Quantity]) /[PYTD Quantity]
- YOY Profit Margin = ([YTD Profit Margin]-[PYTD Profit Margin]) /[PYTD Profit Margin]
- YOY Profit = ([YTD Profit]-[PYTD Profit]) /[PYTD Profit]
- Sales Icon Color = IF([YOY Sales]>0,"Green","Red")
- Quantity Color = IF([YOY Quantity]>0,"Green","Red")
- Profit Margin Color = IF([YOY Profit Margin]>0,"Green","Red")
- Profit Color = IF([YOY Profit]>0,"Green","Red")
- PYTD Sales = CALCULATE(SUM(ecommerce_data[sales_per_order]),SAMEPERIODLASTYEAR(DATESYTD('Calendar'[Date])))
- PYTD Quantity = CALCULATE(SUM(ecommerce_data[order_quantity]),SAMEPERIODLASTYEAR(DATESYTD('Calendar'[Date])))
- PYTD Profit Margin = CALCULATE([Profit Margin],SAMEPERIODLASTYEAR(DATESYTD('Calendar'[Date])))
- PYTD Profit = CALCULATE(SUM(ecommerce_data[profit_per_order]),SAMEPERIODLASTYEAR(DATESYTD('Calendar'[Date])))

```

### Results/Findings/Insights

- Sales and profit vary significantly across regions, with California on top,New York on second and Texas on third.
  
- Office Supplies is driving the highest sales.

- YTD vs PYTD trends show steady sales growth with slight seasonal fluctuations.

- Consumer segment contributes the most to total revenue and profit, followed by Corporate.

- Standard Class is the most preferred shipping mode among customers.

### Recommendations

- Focus marketing efforts on top-performing regions like the California, New York and Texas to maximize revenue.

- Reevaluate pricing and discount strategies for underperforming technology products to improve profitability.

- Optimize shipping operations for Standard Class to maintain customer satisfaction.

### Limitations

- The dashboard relies on historical data, which may not reflect current market conditions.

- Limited data attributes restrict deeper analysis of customer behavior and external factors.





  

