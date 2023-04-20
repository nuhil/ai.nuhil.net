# Data Modeling

Quality data governance requires that the stakeholders within an organization understand its data and that data is managed in a way that supports objectives and goals. These qualities increase the potential for staff to better define data uses to solve business problems. <mark style="background-color:green;">When the business requirements for data are analyzed, and defined in support of an organization, we call this data modeling.</mark>&#x20;

**Skilled data modelers work with business stakeholders, and the end product is a data model.**

## Model Could Be

Conceptual

Logical

Physical

## May Include

Data Description

Constraints

Rules

Defaults Values

Security

**One form of Data Model is called Entity-relationship Diagram (ERD) or ER Diagram.**

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-12 at 1.34.54 PM.png" alt=""><figcaption></figcaption></figure>

## Design Schemas

#### Star Schema

Star Schema is a modeling technique for designing data warehouses that organizes data into a central fact table and a set of dimension tables. The fact table contains the measures or metrics that the business wants to analyze, while the dimension tables contain the attributes that provide context to the measures. This approach provides a simplified, denormalized view of the data that facilitates fast querying and analysis.

Suppose a retail company wants to analyze sales data for their products across different regions and time periods. In a star schema, the fact table would contain the sales data such as revenue and units sold, and the dimension tables would contain the attributes such as product, region, and date. This approach would allow the company to easily analyze sales trends and patterns across different dimensions.

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-15 at 12.14.38 AM.png" alt=""><figcaption></figcaption></figure>

#### Snowflake

Snowflake is the extension of the star schema. It consists of a fact table and dimension tables with snowflake-like layers.

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-15 at 12.15.32 AM.png" alt=""><figcaption></figcaption></figure>

#### Galaxy

The Galaxy schema contains two fact tables, and it shares dimension tables between them.

<figure><img src="../.gitbook/assets/Screen Shot 2023-04-15 at 12.16.08 AM.png" alt=""><figcaption></figcaption></figure>

{% embed url="https://www.guru99.com/star-snowflake-data-warehousing.html" %}
