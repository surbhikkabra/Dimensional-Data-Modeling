![Star schema Design](https://github.com/surbhikkabra/Dimensional-Data-Modeling/blob/readme/image.png?raw=true)


## KEY HIGHLIGHTS OF THE MULTI-FACT SCHEMA

1. Role-Playing Dimensions - Date (Date picked up, Date of Delivery), Customer (Customer Ship to, Customer Ship From), Location (Location Ship to, Location Ship from).
2. Invoice Number is treated as Degenerate Dimension.
3. Many-to-Many Relationship between Customer Dimension and Contract
4. Dimension is captured using a bridge table.
5. Customer type dimension is a permissible outrigger of Customer 
6. Dimension due to its low-cardinality.
7. To track information about deals in existence on any given date, FACT TABLE WILL NOT BE USEFUL as it contains information about only those products which have been shipped. So, for that purpose, we maintain a factless fact table between deal dimension and product dimension. 

