# Perfect Pizza Operation System Analysis and Design

## Table of contents
- [Project Overview](#project-overview) 
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Limitation](#limitation)
- [References](#references)

## Project Overview 

The owner of Perfect Pizza aims to implement an efficient system for managing pizza and Buffalo wing orders. The system's primary objective is to streamline order processing, enhance customer service, and facilitate managerial decision-making through comprehensive data analysis. This system will enable easy retrieval of customer information, computation of final costs, order distribution to cooks, and generation of receipts and promotional offers. Moreover, it will provide management with insights through weekly total reports.

## Data Sources 
The data was created using MySQL.  It was designed to fit the operation system requirement of the Pizza company to run their business effectively.

## Tools 
- MySQL (SQL) - Data generation and Data Analysis 
- Microsoft Excel - Data cleaning, Data formating 

## Data Cleaning and Preparation
### Data Flow Diagram (DFD)

The Data Flow Diagram illustrates the flow of information within Perfect Pizza's system, outlining processes and activities involved in order processing and compani's management.

![DFD ](https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/0e74f36c-a2db-4cee-ba57-cfbc6f70c14d)


### List of Entities
1. Customer Entity:
   Stores customer details including ID, name, phone number, address, last order date, and preferred pizza.                                                                           
2. Orders Entity:
   Records order-specific information such as order ID, customer ID, delivery details, order date, total cost, tax, delivery cost, and assigned driver ID.
3. Cook Entity: 
   Manages cook-related data including cook ID, order ID, cook name, and specialty.
4. Food Entity: 
   Stores food item details like food ID, cook ID, food name, ingredients, and price.
5. Delivery Entity: 
    Manages delivery-related information such as driver ID, driver name, delivery date, receipt ID, coupon ID, order ID, food ID, and payment.
6. Management Entity: 
    Stores managerial data including manager ID, manager name, and weekly total sales, along with driver ID.
 7.PPS Entity: 
    Acts as an intermediary table linking various entities through primary and foreign keys.
List of Primary and Foreign Keys


### SQL Tables

SQL tables are designed and created to efficiently store and manage data related to customers, orders, cooks, food items, deliveries, and managerial activities. Each table is structured with appropriate attributes and relationships, ensuring data integrity and ease of retrieval.
The entities and their respective attributes that make up the data structures in the design are:


1.	Customer entity:
•	cus_ID (primary key)
•	cus_name
•	cus_phone_N
•	cus_address
•	cus_Pizza_name
•	cus_lastOrder_date

2.	Orders entity:
•	order_ID (primary key)
•	cus_ID (foreign key referencing Customer entity)
•	order_address
•	order_phone_N
•	order_Date
•	Total
•	Tax
•	delivery_Cost
•	driver_ID (foreign key referencing Delivery entity)

3.	Cook entity:
•	cook_ID (primary key)
•	order_ID (foreign key referencing Orders entity)
•	cook_name
•	cook_specialty

4.	Food entity:
•	food_ID (primary key)
•	cook_ID (foreign key referencing Cook entity)
•	food_name
•	food_ingr
•	food_price

5.	Delivery entity:
•	driver_ID (primary key)
•	driver_name
•	delivery_date
•	receipt_ID
•	coupon_ID
•	order_id (foreign key referencing Orders entity)
•	food_ID (foreign key referencing Food entity)
•	payment

6.	Management entity:
•	manager_ID (primary key)
•	manager_name
•	weekly_total
•	driver_ID (foreign key referencing Delivery entity)

7.	PPS entity:
•	PPS_ID (primary key)
•	cus_ID (foreign key referencing Customer entity)
•	order_ID (foreign key referencing Orders entity)
•	cook_ID (foreign key referencing Cook entity)
•	food_ID (foreign key referencing Food entity)
•	driver_ID (foreign key referencing Delivery entity)
•	manager_ID (foreign key referencing Management entity)

![image](https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/b3ea496d-e3e8-4c66-b178-08de162e6fd9)


![image](https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/bc08b575-fb10-4320-bd24-6758eaf78ef6)


![image](https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/9c31026c-b2e6-4d24-876f-76e7954dcec9)

## Exploratory Data Analysis
a) Can we generate a each customer's profile?

b) Show the cutomer's orders, the total, tax, delivery_cost  and the driver ID

c) Wich driver made deliveries this week?

d) Show management profile and their weekly sales revenue.

e) Generate a relational Analysis:

<img width="468" alt="image" src="https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/d00c26ec-d4fd-4086-9024-a424ae7a2011">


## Trigger

A trigger named Customer_Order_Trigger is implemented to automate the insertion of customer data into the Customer table when an order is placed without an existing customer ID. This trigger enhances data consistency and eliminates redundancy in customer information management.

- Trigger test Demo
- Insert Code
INSERT INTO Customer (cus_ID, cus_name, cus_phone_N, cus_address, cus_Pizza_name, cus_lastOrder_date)
VALUES
(NULL, "Pamela Love ", "205-765-0045", "864 Fox st, Cherry MD","Cheese Pizza", "2023-03-31");

## Trigger Test Demo

A test scenario is provided to demonstrate the trigger's functionality, showcasing how customer information is automatically inserted upon order placement.

Table Before:

<img width="468" alt="image" src="https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/0e843dda-38e6-4b5d-9832-91a30cda99c9">

Table After Trigger:

<img width="468" alt="image" src="https://github.com/Cagnoro1/Perfect-Pizza-Operation-System-Design/assets/135088212/8bb5368a-2e4c-4f32-b70c-c53b28d22965">


By implementing this system design, Perfect Pizza aims to optimize its operational efficiency, enhance customer satisfaction, and drive informed decision-making through data-driven insights.

