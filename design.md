

![Star schema Design](http://url/to/img.png)


KEY HIGHLIGHTS OF THE MULTI-FACT SCHEMA

Role-Playing Dimensions - Date (Date picked up, Date of Delivery), Customer (Customer Ship to, Customer Ship From), Location (Location Ship to, Location Ship from).
Invoice Number is treated as Degenerate Dimension.
Many-to-Many Relationship between Customer Dimension and Contract Dimension is captured using a bridge table.
Customer type dimension is a permissible outrigger of Customer Dimension due to its low-cardinality.
To track information about deals in existence on any given date, FACT TABLE WILL NOT BE USEFUL as it contains information about only those products which have been shipped. So, for that purpose, we maintain a factless fact table between deal dimension and product dimension. 

