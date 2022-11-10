# Introduction to Data Warehouses

## Objective

- understand the purpose, architecture, and technologies used in a data warehouse.

## Prerequisites

- Relational database design & SQL
- Programming in Python
- Basic familiarity with dimensional modeling

## What is a Data Warehouse? A Business Perspective

- You are in charge of a retailer’s data infrastructure. Let’s look at some business activities.

    - **Customers** should be able to find goods & make orders
    - **Inventory Staff** should be able to stock, retrieve, and re-order goods
    - **Delivery Staff** should be able to pick up & deliver goods
    - **HR** should be able to assess the performance of sales staff
    - **Marketing** should be able to see the effect of different sales channels
    - **Management** should be able to monitor sales growth
    - **Ask yourself:** Can I build a database to support these activities? Are all of the above questions of the same nature?
    - Let's take a closer look at details that may affect your data infrastructure.

## Questions to ask 

- Retailer has a nation-wide presence → How to Scale? Do we decide to have single DB or have many DB across all retail centers?
- Acquired smaller retailers, brick & mortar shops, online store → Single database? Complexity?
- Has support call center & social media accounts → Tabular data?
- Customers, Inventory Staff and Delivery staff expect the system to be fast & stable → Performance
- HR, Marketing & Sales Reports want a lot information but have not decided yet on everything they need → Clear Requirements? May evolve later
- Ok, maybe we can conclude that one single relational database won’t suffice

## DWH Business Operational Vs. Business Analytical process

- From Business perspective, business it just a set of business process
- First we want to separate operational process from analytical process
- We can say Operational process as "Make things work!". We just want to serve the customers. Get job done guy.
    - Find goods and make orders (for customers)
    - Stock and find goods (for inventory)
    - Pick up and deliver goods (for delivery staff)
- We can say Analytical process as "Hey what's going on?". Big picture guy.
    - Assess the performance of sales staff (for HR)
    - See effect of different sales channel (for marketing)
    - Monitor sales growth (for management)

## What happens if we have same data source for operational and analytical process?

<p align="center">
  <img src="images\03-01-01.PNG" />
</p>

- Operational Database
    - Pros
        - excellent for operations
        - no redundancy, high integrity
    - Cons
        - Too slow for analytics
        - Too many joins to obtain desired result
        - Too hard to understand as the DB was modeled with Normal forms
- Having all analytical operations load on the same database where operational process are running will slow down the performance of the database and is not a good idea
- What happens if we use the same database for both OLAP and OLTP?
    - The database schema will be hard to understand for business analysts
    - The analytical queries will be slow as we will have to perform lots of table joins
    - It might be totally ok if the database is small

## Solution : Create 2 processing models, create a system for them to co-exist

- General solution is the data warehouse
- We take the existing operational data sources, trasform it to something else which will be more efficient for analytical process
- Data warehouse is a system (including processes, technologies and data representation) that enables us to support analytical process
- Data warehouse is optimized to support processes for data analysis, has data gathered from multiple sources and is an Online Analytical Processing system.
- 

<p align="center">
  <img src="images\03-01-02.PNG" />
</p>

## Examples

### Operational Process

- Need to track inventory
- Track financial transactions
- Track shipment of customers orders

### Analytical Process

- Examine market segmentation over a period of time
- Split customers into market segments for market optimizations

## What is a Data Warehouse? A Technical Perspective

- (From KIMBALL) A data warehouse is a **copy of transaction data** specifically **structured for query and analysis**
- (From INMON) A data warehouse is a **subject-oriented** (i.e. no one size fits all), **integrated** (information is from many sources), **non volatile** (i.e. data is persistent) and **time-varient** (ask same question on different day and answer is going to change) collection of data in support of management decision
- (From RAINARDI) A data warehouse is a system that **retrieves** and **consolidates** data **periodically** from the source system into **dimensional** or **normalized** data store. It usually **keeps years of history** and is queried for **business intelligence or other analytical activities**. It is typically updated in **batches**, not every time a transaction happens in the source system.

## Data warehouse idea

- First activity is ETL (Extract Transform Load). We **extract** the data and from the source systems used for operations, **transform** the data and **load** it into dimensional model
- The **dimensional model** is designed to 
    - make it easy for business users to work with the data
    - improve analytical queries performance
- The **technologies** used for strong dimensional models are **different** from traditional technologies
- Business-user-facing application are needed, with clear visuals aka BI (Business Intelligence) apps

## Data warehouse goals

- Simple to understand
- Performant
- Quality assured
- Handles new questions well
- Secure

## Dimensional modeling

- 





