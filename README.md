# Metro Management System with Smart Card Integration

A **Core Java + JDBC + MySQL** metro management project designed to be **fully executable from the command line**. No GUI or GUI-based setup is required for evaluation.

## Features

- Passenger registration and login
- Demo passenger login
- Smart card issuance
- Smart card balance display
- Smart card recharge
- Metro station listing
- Metro entry/exit through the terminal
- Automatic fare calculation
- Fare deduction from smart card balance
- Journey history
- Transaction logging in MySQL
- Input validation and database error handling

## Technology Stack

- Java 17+
- Core Java
- JDBC
- MySQL 8+
- MySQL Connector/J 8.x
- Command-line interface (CLI)

## Project Structure

```text
MetroManagementSystem/
├── src/
│   └── metro/
│       ├── Main.java                  # CLI entry point
│       ├── MetroService.java          # Business logic
│       ├── DatabaseConnection.java    # JDBC connection
│       ├── User.java
│       ├── Passenger.java
│       ├── Admin.java
│       ├── SmartCard.java
│       ├── Station.java
│       ├── FareCalculator.java
│       └── ValidationException.java
├── sql/
│   └── metro_system.sql               # Database + tables + demo data
├── docs/
│   ├── Project_Report.docx
│   ├── PROJECT_REPORT.md
│   ├── Metro_Project_PPT.pptx
│   └── UML_Class_Diagram.svg
├── lib/
│   └── mysql-connector-j-8.x.x.jar    # Place the downloaded JDBC driver here
├── run.bat                            # Windows command-line launcher
├── run.sh                             # Linux/macOS command-line launcher
└── README.md
```

## 1. Requirements

Install:

1. JDK 17 or newer
2. MySQL Server 8 or newer
3. MySQL Connector/J

A GUI IDE is **not required**.

## 2. Database Setup

Start MySQL and run:

```sql
SOURCE sql/metro_system.sql;
```

Or from a terminal:

```bash
mysql -u root -p < sql/metro_system.sql
```

The SQL file creates the `metro_system` database and all required tables.

### Demo credentials

Passenger:

```text
Phone:    9999999999
Password: demo123
```

Admin record in the database:

```text
Username: admin
Password: admin123
```

## 3. Configure JDBC

Open:

```text
src/metro/DatabaseConnection.java
```

Set the MySQL username/password for your computer:

```java
private static final String DB_USER = "root";
private static final String DB_PASSWORD = "YOUR_MYSQL_PASSWORD";
```

Do not upload your real database password to GitHub.

## 4. Command-Line Compilation and Execution

### Windows CMD / PowerShell

From the project root:

```bat
mkdir out
javac -d out -cp "lib/mysql-connector-j-8.x.x.jar" src\metro\*.java
java -cp "out;lib/mysql-connector-j-8.x.x.jar" metro.Main
```

### Linux / macOS

```bash
mkdir -p out
javac -d out -cp "lib/mysql-connector-j-8.x.x.jar" src/metro/*.java
java -cp "out:lib/mysql-connector-j-8.x.x.jar" metro.Main
```

Replace `mysql-connector-j-8.x.x.jar` with the exact connector JAR filename you downloaded.

## 5. Launcher Scripts

After placing the JDBC JAR inside `lib/`, you can use:

### Windows

```bat
run.bat
```

### Linux / macOS

```bash
chmod +x run.sh
./run.sh
```

These launch the application directly in the terminal.

## 6. Help Command

```bash
java -cp "out:<connector-path>" metro.Main --help
```

On Windows, use `;` instead of `:` in the classpath.

## 7. Example CLI Flow

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
Enter choice: 5

Demo login successful.

Welcome, Demo Passenger
1. View Smart Card
2. Issue Smart Card
3. Recharge Smart Card
4. Start Journey (Entry)
5. End Journey (Exit)
6. View Stations
7. View Journey History
8. View Fare Information
9. Logout
```

## Fare Rules

| Distance | Fare |
|---|---:|
| 0–5 km | ₹10 |
| Above 5–10 km | ₹20 |
| Above 10–20 km | ₹30 |
| Above 20 km | ₹40 |

The distance is calculated from the station's stored distance from the route origin.

## OOP Concepts Demonstrated

- Abstraction: `User` is an abstract class
- Inheritance: `Passenger` and `Admin` extend `User`
- Encapsulation: model classes use private fields and public methods
- Polymorphism: `getRole()` is overridden by subclasses
- Exception handling: `ValidationException` and SQL exception handling
- Collections: `List<Station>`
- JDBC: database connectivity, prepared statements, transactions

## Evaluation Note

The primary executable entry point is:

```text
metro.Main
```

It is a **console application** and does not create a Swing/AWT window. The project can therefore be compiled and run from a terminal, satisfying the command-line executability requirement.

## Security Note

This is an academic project. Passwords are stored as plain text in the sample database for simplicity. A production system should use password hashing, environment variables/secrets, stronger validation, and proper access control.
