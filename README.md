# Financial Summary Dashboard

### Dashboard Link :https://drive.google.com/file/d/1JujSJphhlR2FES95QQxPxmldguMbF-9e/view?usp=sharing

## Problem Statement

Our organization requires a comprehensive report on recent sales performance to gain actionable insights. Specifically, we need to analyze the data to answer the following key questions:

1) Identify the month and year with the highest profit.
2) Determine the top-performing countries or regions in terms of sales success.
3) Recommend which products and market segments merit continued investment based on current performance metrics.
4) The report should be presented in Power BI, providing interactive visuals that allow stakeholders to explore the data dynamically.

It should also include an executive summary page summarizing the findings for each question concisely and a Profit and loss page finding the profits from the top performing products and Year over Year(YoY) performance.




### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a Excel file.
- Step 2 : Prepare the data
           
           -->Select the Financials table, and choose Transform Data.
           -->Select the Units Sold column and changed the datatype to whole number.
           -->In the Product column, select the dropdown and clear the box next to Montana.
         Note:  We know the Montana product 
- Step 3 : Calculated measure was created in which, expression wrote to add all the numbers in the Units Sold column

for creating new measure following DAX expression was written;
       
        Total Units Sold = SUM(financials[Units Sold])

![Screenshot 2024-05-18 165030](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/8c31356e-ea4d-42e1-a746-a4be965fb33f)

- Step 4 : New expression was created to generate a Calendar table of all dates between January 1, 2013, and December 31, 2014.

Following DAX expression was written for the same,
        
        Calendar = CALENDAR(DATE(2013,01,01),Date(2014,12,31))
        
Slicers were used to represent the years and months and quarter for the charts and graphs.

![Screenshot 2024-05-18 154300](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/f5b7eb1d-102e-44df-98ab-002f6bddaaeb)
       
 - Step 5 : create a relationship between both the tables from Date to Date field.

![Screenshot 2024-05-18 155058](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/0c52a3d5-0a61-480b-9645-99a9f4c962f8)

Few measures calculated to find the sum:
       
       i)Total COGS = SUM(financials[COGS])
       ii)Total Discounts = SUM(financials[Discounts])
       iii)Total Gross Sales = SUM(financials[Gross Sales])
       iv)Total Profit = SUM(financials[Profit])
       v)Total Sales = SUM(financials[ Sales])
       vi)Total Revenue = SUM(financials[ Sales])
       vii)Previous Year Revenue = CALCULATE([Total Revenue],DATEADD('Calendar'[Date],-1,YEAR))
 
 - Step 6 : Building report, to find the answers of the above mentioned questions and visualize,below is a snap of the final Summary Report,

 ![Screenshot 2024-05-18 160112](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/b810013a-8d37-4c69-9137-285f3727db47)


 Now that the Summary is done, there is one more page to show the Profit and Loss happened

 Note: This is my own approach as a beginner and my first ever PBI Dashboard.


- Step 7: Some important calculations made using DAX measures is shown below:

        -->to find YoY Variance: Yoy Variance = [Total Revenue] - [Previous Year Revenue]
        -->to find Margin%: Margin Percentag (%) = DIVIDE(SUM(financials[ Sales]) - SUM(financials[COGS]),SUM(financials[ Sales])) * 100
        -->to find the loss per product: Loss Per Product = SUM(financials[COGS]) - SUM(financials[ Sales])

 A card visual was used to represent the Margin %,below is the snap!

 ![Screenshot 2024-05-18 163405](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/b146a02a-07bc-43bc-9db2-c84958eb4f51)
 
 A card visual was used to represent the YoY Variance from the previous year,below is the snap!

 ![Screenshot 2024-05-18 163533](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/521e4235-8ccf-486d-bb87-d5e2e9aca350)

 
Excited to see the final dashboard.......

VOILA...!!!Here it is!

![Screenshot 2024-05-18 163306](https://github.com/prachiprabha-s/Power-BI-Financial-Dashboard/assets/168185906/9afdbe38-24a8-40a7-b586-3564ecce5171)

Note: I know this is not perfect and there is lot to learn but hey, it is not that bad as a beginner level. I would be happy for your guidance. Thanks in advance.

# Insights


1) For each product we could see the total of COGS, Sales, revenue and Profit Margin in the table chart.

2) We could also see the top 3 product quantity sold by profit which I think is a really cool finding and vice versa for the bottom.

3) We can also see a Line Chart defining the loss per product and total revenue by year and month.

4) We also calculated the loss per product using a column chart.

And few slicers for same as the Summary report .
