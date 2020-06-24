# Dimensional-Data-Modeling

##Problem Statement

Given a shipment company that serves a limited group of customers design a dimensional model with invoice line as the grain of the fact table. We then need to query data for reporting and analytical purposes. Some queries that we may be interested in:  query by customer type, product category, region, year, shipment mode, contract terms for measures like :discount, ship weight, volume, delay in delivery, revenue.  

**A shipment invoice contains the following information:**

Invoice Number
Date Picked Up
Date of Delivery
Ship From Customer
Ship To Customer
Ship From Warehouse
Ship From City
Ship To City
Shipment Mode (like air/sea/truck/train)
Shipment Class (codes like 1,2,3 which translate to express, expedited, standard)
Contract ID
Total Shipping Charges
Deal ID  (refers to a discount deal in effect)
Discount Amount
Taxes
Total Billed Amount
Total Ship Weight
Total Ship Volume

##Assumptions

1. Quantity is number of items. i.e  you do not have to worry about unit measure issues.
    Discount and Taxes can be allocated per line.
    

2. All the customers are registered with the company and treated as a single table of customers. For our model, we assume any customer may ship items to any other customer.  Customer is a large, single table.

3. Customer table also contains info on:
   - customer size (small, medium or large)
   - customer ship frequency (low, medium, or high)
   - credit status(excellent, good, average)
These tend to be correlated; for example,  large customers tend to be high frequency and have excellent or good credit status.  

4. Contract -  number of contracts is relatively small. Each customer may have multiple contracts.
5. Deal -  number of Deals is relatively small. Some shipments may have no deal applicable.  We do want to query information like total revenue by deal. 6. For a given product, source-city, destination-city, and date, we can identify the deal in existence, if any.  You can simplify source-city to be source-warehouse if you want.

7. Ship from city is same as the city where the Warehouse is. (not the city where Ship-From Customer is.)

8. We can find an Estimated Date of Delivery for each shipment from operational systems, even though it is not printed on the invoice.

9. There is some correlation present among Shipment Mode, and Shipment Class.

10. Products roll up to brand, category.  Warehouses roll up to subregion, region, territory.






