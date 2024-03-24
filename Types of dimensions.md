In a relational database used for data warehousing and business intelligence, dimension tables and fact tables play different but complementary roles in organizing and storing data.

**Dimension Table:**

Dimension tables contain descriptive attributes or characteristics about the business entities being analyzed.
They provide context for the measurements stored in fact tables.
Dimension tables typically have a primary key that uniquely identifies each record and may contain additional attributes.
Examples of dimension tables include product, customer, time, location, and employee tables.
Dimension tables are often smaller in size compared to fact tables.
These tables are often denormalized to improve query performance, allowing redundant data storage for ease of querying.

**Fact Table:**

Fact tables store quantitative data, typically numerical measurements or metrics, known as facts.
Facts are usually numeric values that represent business transactions, events, or observations.
Fact tables typically contain foreign keys referencing the primary keys of dimension tables, establishing relationships between facts and dimensions.
Fact tables often contain measures, which are the numeric values that represent the quantitative data being analyzed.
Fact tables can be quite large, as they store detailed information about business events or transactions.
Examples of fact tables include sales transactions, inventory movements, web traffic logs, and financial transactions.

**Types of Dimensions**

Major Types of Dimensions in a Data Warehouse
* Slowly Changing Dimension
* Conformed Dimension
* Degenerate Dimension
* Junk Dimension
* Role-playing Dimension
* Static Dimension
* Shrunken Dimension

There are majorly 3 types of Slowly Changing Dimension tables.

**SCD Type 1**

In this, no history is stored. If we take Address Dimension as an example then in that we do not store any address history of an individual. The dimension table consists of only the latest address of the individual.
This approach is easy to design and saves storage!

**SCD Type 2**

This is the most commonly used type out of all these. In this approach complete history is maintained along with dates to identify from when to when the record is valid. They are usually called start_date and end_date. If the end date is empty then that means that is the active record!
In Address example, if John moves John moves from New York to Boston then Address Dimension would store from when to when John lived in New York and from when he started living in Boston.
This approach takes lots of storage.

**SCD Type 3**

In this, only a limited history is stored. Let's say a business wants to keep only the current address and previous address of the individuals and they do not care to store all of the previous addresses.
This is usually achieved by adding additional columns to store the previous address. This approach falls in-between Type 1 and Type 2!
Compared to Type 2, this approach is easier to design and takes less storage space.

