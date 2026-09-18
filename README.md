# Metro Management System with Smart Card Integration

## Overview

**Metro Management System with Smart Card Integation** is a **command-line based Core Java application** designed to manage metro passengers and automate smart-card based fare processing.

The system allows passengers to register, log in, obtain a smart card, recharge their balance, enter and exit metro stations, and automatically calculate and deduct fares based on travel distance.

The project demonstrates **Core Java, Object-Oriented Programming, JDBC, MySQL connnectivity, exception handling, and command-line application development**.

## Features

- Passenger registration
- Passenger login
- Demo passenger login
- Admin management
- Smart-card issuance
- Smart-card balance checking
- Smart-card recharge
- Smart-card blocking
- Station listing
- Metro entry and exit
- Distance-based fare calculation
- Automatic fare deduction
- Journey history
- Transaction records
- Input validation
- Exception handling
- MySQL database storage
- Command-line interface

## Fare Structure

| Travel Distance | Fare |
|---|---:|
| 0–5 km | ₹10 |
| Above 5–10 km | ₹20 |
| Above 10–20 km | ₹30 |
| Above 20 km | ₹40 |

## Technologies Used

- Java 17+
- Core Java
- Object-Oriented Programming
- JDBC
- MySQL 8+
- Java Collections
- Exception Handling
- Command-Line Interface
- Git & GitHub

## Project Structure

```text
MetroManagementSystem/
│
├── src/
│   └── metro/
│       ├── Main.java
│       ├── MetroService.java
│       ├── DatabaseConnection.java
│       ├── User.java
│       ├── Passenger.java
│       ├── Admin.java
│       ├── SmartCard.java
│       ├── Station.java
│       ├── FareCalculator.java
│       └── ValidationException.java
│
├── sql/
│   └── metro_system.sql
│
├── docs/
│   ├── Project_Report.docx
│   ├── PROJECT_REPORT.md
│   ├── Metro_Project_PPT.pptx
│   └── UML_Class_Diagram.svg
│
├── run.bat
├── run.sh
└── README.md
```

## Project Architecture

The application follows a modular Core Java architecture.

### Model Classes

- `User`
- `Passenger`
- `Admin`
- `SmartCard`
- `Station`

### Service Class

- `MetroService`

Handles registration, login, smart-card management, journeys, fare deduction, and transaction processing.

### Utility Classes

- `DatabaseConnection`
- `FareCalculator`

### Exception Class

- `ValidationException`

### Main Application

- `Main`

Provides the complete command-line interface and controls the application flow.

## Database

The application uses **MySQL** for persistent data storage through JDBC.

### Database Name

```text
metro_system
```

### Main Tables

- `admins`
- `passengers`
- `stations`
- `smart_cards`
- `transactions`
- `journeys`

Foreign keys are used to establish relationships between passengers, smart cards, stations, journeys, and transactions.

## Requirements

Before running the project, install:

1. Java JDK 17 or later
2. MySQL Server 8 or later
3. MySQL Connector/J 8.x
4. Git (optional)

> **Maven is not required for this project.**

## Database Setup

### 1. Start MySQL

Make sure the MySQL server is running.

### 2. Run the SQL Script

The complete database setup script is:

```text
sql/metro_system.sql
```

The script creates the database, tables, relationships, sample stations, demo passenger, smart card, and administrator.

You can run it using MySQL:

```sql
SOURCE sql/metro_system.sql;
```

Alternatively, open the SQL file in MySQL Workbench and execute it.

## Database Configuration

Open:

```text
src/metro/DatabaseConnection.java
```

Update the database credentials:

```java
private static final String URL =
    "jdbc:mysql://localhost:3306/metro_system";

private static final String DB_USER = "root";

private static final String DB_PASSWORD = "your_password";
```

Replace `your_password` with your local MySQL password.

# Command-Line Execution

This project is designed to be **fully executable through the command line without requiring a GUI-based setup**.

The main entry point is:

```text
metro.Main
```

The application uses standard Java console input/output.

## Windows

Using the provided script:

```bash
run.bat
```

Or compile and run manually:

```bash
mkdir out
```

```bash
javac -d out -cp "lib/mysql-connector-j-8.x.x.jar" src/metro/*.java
```

```bash
java -cp "out;lib/mysql-connector-j-8.x.x.jar" metro.Main
```

Replace the JAR filename with the exact MySQL Connector/J version downloaded.

## Linux / macOS

```bash
chmod +x run.sh
./run.sh
```

Or manually:

```bash
mkdir out
```

```bash
javac -d out -cp "lib/mysql-connector-j-8.x.x.jar" src/metro/*.java
```

```bash
java -cp "out:lib/mysql-connector-j-8.x.x.jar" metro.Main
```

## Application Menu

When the application starts:

```text
===============================================
          METRO MANAGEMENT SYSTEM
        Smart Card Integration - CLI
===============================================

--------------- MAIN MENU ----------------
1. Passenger Login
2. Register Passenger
3. View Stations
4. Fare Information
5. Demo Login
0. Exit
-------------------------------------------
Enter choice:
```

After logging in, passengers can access smart-card and journey-related operations.

## Demo Credentials

### Demo Passenger

```text
Phone: 9999999999
Password: demo123
```

### Demo Administrator

```text
Username: admin
Password: admin123
```

## Passenger Workflow

```text
Register / Login
       ↓
Obtain Smart Card
       ↓
Check Card Balance
       ↓
Recharge Card
       ↓
Select Entry Station
       ↓
Enter Metro
       ↓
Select Exit Station
       ↓
Calculate Distance
       ↓
Calculate Fare
       ↓
Deduct Fare
       ↓
Store Journey
       ↓
View Journey History
```

## Testing

The following functionality should be tested:

- Passenger registration
- Passenger login
- Invalid login handling
- Smart-card creation
- Smart-card balance checking
- Card recharge
- Station listing
- Metro entry
- Metro exit
- Fare calculation
- Automatic balance deduction
- Journey history
- Transaction records
- Invalid input handling
- Insufficient balance handling
- Card status validation

### Example Fare Tests

```text
Distance = 3 km   → ₹10
Distance = 7 km   → ₹20
Distance = 15 km  → ₹30
Distance = 25 km  → ₹40
```

## OOP Concepts Demonstrated

### Abstraction

The `User` class is an abstract class containing common properties and behaviour for users.

### Inheritance

`Passenger` and `Admin` extend the `User` class.

```text
          User
         /    \
        /      \
 Passenger     Admin
```

### Polymorphism

The `getRole()` method is implemented differently by different subclasses.

### Encapsulation

Class fields are declared private and accessed through getters and setters.

### Exception Handling

The project uses standard Java exceptions and the custom `ValidationException` class to handle invalid inputs and application errors.

## JDBC and Database Connectivity

The project uses **JDBC (Java Database Connectivity)** to communicate with MySQL.

The application performs operations such as:

- Creating passenger records
- Reading passenger information
- Creating smart cards
- Updating card balances
- Recording transactions
- Recording journeys
- Retrieving journey history
- Reading station information

## Screenshots

Screenshots can be added to demonstrate:

- Main menu
- Passenger registration
- Passenger login
- Smart-card creation
- Card balance
- Card recharge
- Station listing
- Metro entry
- Metro exit
- Fare calculation
- Fare deduction
- Journey history
- Transaction history
- Invalid input handling

## Future Scope

- NFC-based smart-card scanning
- QR-based metro entry
- Mobile application
- Online payment gateway
- Monthly metro passes
- Real-time train tracking
- Travel analytics
- Secure password hashing
- Admin dashboard
- Multiple metro lines
- Dynamic fare management

## Conclusion

The **Metro Management System with Smart Card Integration** provides a practical implementation of a smart-card based metro workflow using **Core Java and MySQL**.

The project demonstrates **Object-Oriented Programming, inheritance, abstraction, polymorphism, encapsulation, JDBC connectivity, exception handling, database management, and modular programming**.

The application is implemented as a **command-line based system**, allowing it to be compiled and executed directly from a terminal without requiring a GUI-based setup.

The system automates passenger management, smart-card operations, metro journeys, fare calculation, balance deduction, and journey record management, providing a complete demonstration of a database-driven Core Java application.
