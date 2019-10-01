# Northwind Traders

For this project, we'll be working with the Northwind database--a free, open-source dataset created by Microsoft containing data from a fictional company. Queries will be made using the python library SQlite3 Here's the schema for the Northwind database:

## Northwind Traders Database - ERD

<img src='Northwind_ERD.png'>

The goal of this project is to test our ability to gather information from a real-world database and use our knowledge of statistical analysis and hypothesis testing to generate analytical insights that can be of value to the company.

The methodology used in this project is to perform  A/B hypothesis testing to answer basic questions about data contained in the database and drawing our conclusions based on whether we REJECT or FAIL TO REJECT the Null Hypothesis

## Questions Asked

1. Do discounts have a statistically significant effect on the number of products customers order? If so, at what level(s) of discount?
2. Do certain product categories sell better in the Americas or Europe?
3. Do late deliveries effect Customer's ordering?
4. Does Number of Territories for each employee affect their sales figures?

## Full Code and Analysis

https://github.com/ktzioumis/Northwind-Traders/blob/master/Northwind.ipynb

### Q1 - Do discounts have a statistically significant effect on the number of products customers order? If so, at what level(s) of discount?

<img src = '/images/discounts_distplot.PNG'>

At a discount rate of 0.05 a 2 sided t-test yields a p-value of 0.0022 which is leads us to REJECT the null hypothesis<br>
At a discount rate of 0.1 a 2 sided t-test yields a p-value of 0.0375 which is leads us to REJECT the null hypothesis<br>
At a discount rate of 0.15 a 2 sided t-test yields a p-value of 0.0002 which is leads us to REJECT the null hypothesis<br>
At a discount rate of 0.2 a 2 sided t-test yields a p-value of 0.0008 which is leads us to REJECT the null hypothesis<br>
At a discount rate of 0.25 a 2 sided t-test yields a p-value of 0.0002 which is leads us to REJECT the null hypothesis<br>

<img src = '/images/discount_rates.PNG'>

Order Value intially increases as the increase in sales volume more than makes up for the lower per unit price but the trend reverses at discount rate of 0.20 and higher as the effect of the discounted price overtakes the increased sales volume.

A peak is observed at a discount rate 0.05. At this discount rate Order value is optimised.

### Q2 - Do certain product categories sell better in the Americas or Europe?

<img src = '/images/produce.PNG'>

For Produce a 2-sided Welch's t-test yields a p-value of 0.0174 from which we REJECT the Null Hypothesis. 
Therefore we conclude there is a difference between buying patterns between Europe and the Americas for Produce items.
                                 
### Q3 - Do late deliveries effect Customer's ordering?

<img src = '/images/late.PNG'>

t-test p-value: 0.0011, therefore we REJECT the Null Hypothesis
Those customers who have received late orders have a different ordering behaviour from those that have had their deliviries arrive on time.<br>The mean order value for Customers who have had orders arrive late is higher than for those that that have not this is counter intuitive at first glance but could be indicative of other factors. For instance, larger order may be more difficult to collect and prepare for delivery on time, larger orders may require different transport methods that may be slower by necessity or customers that have had late orders may be inclined to order less frequently but in larger quantities.

### Q4 - Does Number of Territories for each employee affect their sales figures?

This will be done in with 2 approaches. <br>
by Analysis of Variance by employee sum total of order values and Number of Territories assigned to that employee
and by Analysis of Variance of Order Value and Num of Territories assigned to employee that placed order

<img src = '/images/orderq_numt.PNG'>

<img src = '/images/orderv_numt.PNG'>

Both methods of analysis fail to reject the null hypothesis. There is insufficient statistical evidence that The Nubmer of Territories assigned to an Employee is linked to the Value of Orders placed with that Employee OR to the sum of the Order Value placed with that employee

## Conclusions
1. All Discount levels lead to increased Sales Quantities over no discount. This study recommends a 0.05% level of Discount to achieve optimum Order Value.
2. Buying patterns for product types are not statistically different between Europe and The Americas EXCEPT in the case of Produce.
3. Customers that have received late orders have different buying behaviour from those that have not
4. There is no relationship between The number of Territories assigned to an Employee and the value of orders placed by that Employees or the total value of all the orders placed with that employee

### Future Work/Recommendations
1. Further analysis of discount levels by product or product type, by customer, by region etc. to fine tune optimal discount level
2. Further analysis of Produce buying patterns in Americas and Europe to account of seasonality of fresh goods
3. Further analysis of Customer orders into before/after late order to see effect of order lateness on buying patterns
4. Further analysis of late order characteristics
5. Employee performance metrics should not necessarily be based on number of Territories assigned to Employee. 
6. The distribution of Territories to Employees still needs to be determined