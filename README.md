# Database-Design-for-Globus-Bank-

Table of Contents

1.	Introduction
1.1 Overview of the Project
1.2 Objective of the Project
1.3 Scope of the Database
2.	Database Design
2.1 Database and Table Structure
2.2 Description of Tables
2.3 Summary of Relationships
2.4 Relationships Between Tables
2.5 Constraints and Data Integrity
2.6 Normalization
2.6.1 First Normal Form (1NF)
2.6.2 Second Normal Form (2NF)
2.6.3 Third Normal Form (3NF)
3.	SQL Queries and Data Manipulation
3.1 Data Insertion
3.2 Data Retrieval
3.3 Data Update
3.4 Aggregate Functions and Reporting
4.	Business Use Cases
4.1 Customer Account Management
4.2 Loan Processing and Repayment Tracking
4.3 Transaction History
4.4 Financial Reporting
5.	Conclusion
5.1 Summary of Key Features
5.2 Future Enhancements
5.3 Endnote

### Overview of the Project
The "Bank Database Design for Globus Bank" project presents a comprehensive relational database structure designed to manage essential banking operations such as customer management, accounts, transactions, loans, and branches. The system ensures efficient storage and retrieval of critical data in a secure and scalable manner.

### Objective of the Project
The objective of this project is to create a robust database schema that reflects the core functions of a bank, focusing on:
•	Managing customer information
•	Handling various types of bank accounts
•	Tracking transactions
•	Managing loans and repayments
•	Storing branch information

### Scope of the Database
The scope includes five primary tables:
1.	**Customers** – Stores personal information of customers.
2.	**Branches** – Contains data related to the bank’s branches.
3.	**Accounts** – Manages customer bank accounts.
4.	**Transactions** – Records all transactions made by customers.
5.	**Loans** – Handles loan-related data, including amounts, types, and status.

### Database and Table Structure
The database, named Globus Bank Ltd Database, consists of five tables. 

### Table Description
#### Customers Table

| Column            | Data Type           | Constraints                        |
|-------------------|---------------------|------------------------------------|
| customer_id       | INT                 | PRIMARY KEY, AUTO- INCREMENT       |
| first_name        | VARCHAR (100)       | NOT NULL                           |
| last_name         | VARCHAR (100)       | NOT NULL                           | 
| date_Of_birth     | DATE                | NOT NULL                           |
| Email_Address     | VARCHAR (100)       | UNIQUE, NOT NULL                   | 
| Phone_Number      | VARCHAR (11)        | UNIQUE, NOT NULL                   |
| date_created      | DATE                | NOT NULL                           |

#### Branches Table

| Column            | Data Type           | Constraints                        |
|-------------------|---------------------|------------------------------------|
| branch_id         | INT                 | PRIMARY KEY, AUTO- INCREMENT       |
| branch_name       | VARCHAR (100)       | NOT NULL                           |
| branch_location   | VARCHAR (100)       | NOT NULL                           | 
| contact_number    | VARCHAR (15)        | NOT NULL                           | 

#### Accounts Table

| Column            | Data Type           | Constraints                                                |
|-------------------|---------------------|------------------------------------------------------------|
| account_ID        | INT                 | PRIMARY KEY, AUTO- INCREMENT                               |
| account_number    | VARCHAR (10)        | UNIQUE, NOT NULL                                           |
| customer_id       | INT                 | FOREIGN KEY REFERENCES Customers                           |
|branch_id          | INT                 | FOREIGN KEY REFERENCES Branches                            |
| account_type      | VARCHAR (50)        | CHECCK IN ('Savings', 'Current', 'Fixed Deposit'), NOT NULL|
| balance           | DECIMAL             | NOT NULL                                                   |
| date_opened       | DATE                | NOT NULL                                                   |

#### Transactions Table

| Column                  | Data Type           | Constraints                                                |
|-------------------------|---------------------|------------------------------------------------------------|
| transaction_id          | INT                 | PRIMARY KEY, AUTO- INCREMENT                               |
| account_id              | INT                 | FOREIGN KEY REFERENCES Accounts                            |
| transaction_type        | VARCHAR (50)        | CHECCK IN ('Savings', 'Current', 'Fixed Deposit'), NOT NULL|
| amount                  |  DECIMAL            | NOT NULL                                                   |
| transaction_date        | DATE                | NOT NULL                                                   |
| transaction_description | DECIMAL             | NOT NULL                                                   |

#### Loans Table

| Column                  | Data Type           | Constraints                                                |
|-------------------------|---------------------|------------------------------------------------------------|
| loan_id                 | INT                 | PRIMARY KEY, AUTO- INCREMENT                               |
| customer_id             | INT                 | FOREIGN KEY REFERENCES Customers                           |
| loan_amount             | DECIMAL             | NOT NULL                                                   |
| interest_rate           | DECIMAL             | NOT NULL                                                   |
| loan_status             | VARCHAR             | CHECCK IN ('Active', 'Settled', 'Overdue'), NOT NULL       |
| start_date              | DATE                | NOT NULL                                                   |
| due_date                | DATE                | NOT NULL                                                   |




