# Perfect-Pizza-Operation-System-Design
In this project, we use MySQL to code to create a system to make a Pizza company run their business effectively.


# Executive Summary

Perfect Pizza aims to implement an efficient system for managing pizza and Buffalo wing orders. The system's primary objective is to streamline order processing, enhance customer service, and facilitate managerial decision-making through comprehensive data analysis. This system will enable easy retrieval of customer information, computation of final costs, order distribution to cooks, and generation of receipts and promotional offers. Moreover, it will provide management with insights through weekly total reports.

# System Initiation

# Data Flow Diagram (DFD)

The Data Flow Diagram illustrates the flow of information within Perfect Pizza's system, outlining processes and activities involved in order processing and compani's management.

# List of Entities
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

Customer:
Primary Key: cus_ID
Orders:
Primary Key: order_ID
Foreign Key: cus_ID (references Customer(cus_ID))
Foreign Key: driver_ID (referencing Delivery(driver_ID))
Cook:
Primary Key: cook_ID
Foreign Key: order_ID (references Orders(order_ID))
Food:
Primary Key: food_ID
Foreign Key: cook_ID (references Cook(cook_ID))
Delivery:
Primary Key: driver_ID
Foreign Key: order_ID (references Orders(order_ID))
Foreign Key: food_ID (references Food(food_ID))
Management:
Primary Key: manager_ID
Foreign Key: driver_ID (references Delivery(driver_ID))
PPS:
Primary Key: PPS_ID
Foreign Keys linking to various entities.

# SQL Tables

SQL tables are designed and created to efficiently store and manage data related to customers, orders, cooks, food items, deliveries, and managerial activities. Each table is structured with appropriate attributes and relationships, ensuring data integrity and ease of retrieval.

# Trigger

A trigger named Customer_Order_Trigger is implemented to automate the insertion of customer data into the Customer table when an order is placed without an existing customer ID. This trigger enhances data consistency and eliminates redundancy in customer information management.

# Trigger Test Demo

A test scenario is provided to demonstrate the trigger's functionality, showcasing how customer information is automatically inserted upon order placement.

By implementing this system design, Perfect Pizza aims to optimize its operational efficiency, enhance customer satisfaction, and drive informed decision-making through data-driven insights.

