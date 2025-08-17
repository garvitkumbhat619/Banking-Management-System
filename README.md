# Banking Management System (Python + MySQL)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8%2B-orange)](https://www.mysql.com/)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-informational)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
__________
A **Virtual Bank**—*COLONY BANK OF INDIA*—built with **Python (frontend/CLI)** and **MySQL (backend)**.  
It provides **secure authentication** and **full CRUD** on customer records, with transaction tracking and robust error handling aimed at bank staff.

## ✨ Features

- 🔐 **Auth**: Login/Signup for authorized staff
- 👤 **Customers**: Create, Read, Update, Delete customer records
- 💸 **Transactions**: Deposit / Withdraw with running balance
- 📜 **History**: View overall or per-account transaction details
- 🧾 **Loans**: Update/maintain simple loan info (if implemented in your code)
- 🧯 **Safety**: Extensive exception handling for a user-friendly CLI
---
## 🧱 Tech Stack

- **Language**: Python
- **Database**: MySQL
- **Python Modules**: `datetime`, `mysql.connector`  
  *(optional but recommended: `python-dotenv`, `prettytable`, `colorama`)*
---
## ⚙️ Requirements

- Python (3.8+ recommended)
- MySQL Server (local)
- MySQL Connector for Python
- Editor: VS Code / IDLE
---
## 🗄️ Database Setup
```bash
CREATE DATABASE IF NOT EXISTS hubnet;
USE hubnet;

-- Bank Table
CREATE TABLE IF NOT EXISTS bank (
  name           VARCHAR(30),
  username       VARCHAR(30) PRIMARY KEY,
  password       TINYTEXT,
  date_of_birth  DATE,
  address        VARCHAR(40),
  mobile_number  VARCHAR(30),
  aadhar_no      VARCHAR(30),
  balance        INT
);

-- Transaction Table
CREATE TABLE IF NOT EXISTS transaction (
  id         INT AUTO_INCREMENT PRIMARY KEY,
  credited   INT,
  debited    INT,
  username1  VARCHAR(30),
  ts         TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (username1) REFERENCES bank(username)
);
``` 
- UserName is the Primary Key in Bank Table  and UserName1 is the Foreign key in  Transaction Table.
- Before Running This Code in Your System Make Sure you have created the bank and transactions Table.
---
## ▶️ Running the App
```bash
python src/bank_project.py
# or if everything is in one file:
# python Bank-Project.py
```
- Ensure MySQL is running and the hubnet DB/tables exist.
---
## 🧩 ER Diagram (Conceptual)
```bash
+---------+               +--------------+
|  bank   |               | transaction  |
+---------+               +--------------+
| username|<--+       +---| username1    |
| name    |   |       |   | credited     |
| dob     |   | 1   n |   | debited      |
| address |   +-------+   | ts           |
| mobile  |               | id (PK)      |
| aadhar  |               +--------------+
| balance |
+---------+
(PK: username)
```
---
## Some Glimpse of this project are shown below

<img width="960" alt="DEMO1" src="https://user-images.githubusercontent.com/110014127/187087816-6f230993-c3f2-4816-baa9-1834c84bf2d1.png"><img width="960" alt="DEMO2" src="https://user-images.githubusercontent.com/110014127/187087821-5ae8a0b6-dcf3-463d-a492-da88e3d65447.png"><img width="960" alt="DEMO3" src="https://user-images.githubusercontent.com/110014127/187087834-994a3814-2f92-49dd-a6a5-d56422d92027.png">


<img width="960" alt="DEMO4" src="https://user-images.githubusercontent.com/110014127/187087837-6e3e3e7b-a110-4eef-9479-426511fb55f3.png">

<img width="960" alt="DEMO5" src="https://user-images.githubusercontent.com/110014127/187087843-c6a1af98-d81f-4a99-ae44-8a7853130eeb.png">

- Properties of Table In MY SQL Database:

<img width="960" alt="MY SQL DATABASE" src="https://user-images.githubusercontent.com/110014127/187087967-35e7bbb6-219e-4eb5-8238-a3e90b006e8b.png">
