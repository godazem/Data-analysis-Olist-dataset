# Data analysis of public Olist e-commerce data

## Introduction
This repository presents a set of files where I practised my SQL queries using BigQuery on the Olist E-commerce database and also provided some visualisations and insights from this analysis by using Microsoft Excel and PowerPoint.


## Data
The whole database has 11 datasets which contain different information of customers, sellers, orders procedure, etc. This repository, however, does not use all of this data. My chosen area is sellers, so you will see this topic explored deeper with its related datasets.

### Data source:
1. [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/olistbr/brazilian-ecommerce)

### Relational Schema:
![image](https://user-images.githubusercontent.com/105608147/198329924-9352001a-e2d0-482c-9005-102c1c77784f.png)

### Analysis area: SELLERS
Topics explored: Shipping, on-time delivery rate, revenue

### Tables used
1.  olist_orders_dataset (renamed to orders)
2. olist_order_items_dataset (renamed to order_items)
3. olist_products_dataset (renamed to products)
4. product_category_name_translation (renamed to translation).

### Main questions raised before analysis:
How fast is it for customers to receive an order?
Do usually merchants handle the order to logistics partner before the shipping limit date?
Does Pareto principle apply to sellers and revenue?


## Notes on data
Olist is neither an E-commerce company nor a marketplace itself. Olist provides a platform for merchants to sell their products online within a marketplace. So, in this database there are three stakeholders: Olist, merchants or sellers, and the final customers or consumers. Here, merchants are Olist direct customers from where it makes profits.

From Olist website we know how merchants process an order on Olist platform.
When customers place an order, and it has been approved, the seller is responsible for packaging the product and taking it to the Olist logistics operator within a specified period.
The logistics operator is then responsible for sending the products to the customers.

![image](https://user-images.githubusercontent.com/105608147/198332253-129cb55f-f2ea-4594-8ce8-0118e82229ff.png)


## Findings
1. When analysing data we can see that there are some rows in dataset when timestamps look illogical.
Order had to follow this sequence:
Approved >> dropped off by the sender at logistic operator >>> customer received their order.  
Mismatched date entries in the firm’s records indicate some issues that need to be tackled so that the system is more optimized.
Olist should create a more organized and standardized date reporting system so that all the dates entered would be consistent - not earlier than a previous step timestamp.

2. Top 551 sellers (out of 2970) comprise roughly 80% of total revenue. That is ~19% of all sellers, so essentially we can conclude Pareto principle applies in this case, meaning 20% sellers control 80% of the sales and business is doing a good job.

3. Most orders were delivered in 2 weeks (37.73%) after customer’s purchase.

4. 97.63% merchants met the shipping deadline in August 2018, which is very high.

## Further possible analysis
My analysis indicated many on-time deliveries (estimated date after delivery date) but it might be happened due to ineffective method for predicting delivery.

It might be that company has an obsolete software to estimate delivery times. It would be good to check the pattern of estimated date calculation. Long estimated delivery time in turn can deter many buyers.

Also, it would be useful to analyse months with higher percentage of late deliveries and more profitable months. Maybe Olist could hire some contract/ part-time delivery people or distributors to reduce the number of late deliveries and increase profit.
