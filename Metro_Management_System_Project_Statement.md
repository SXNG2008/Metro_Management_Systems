# PROJECT STATEMENT

# Metro Management System with Smart Card Integration

## 1. Problem Statement

Traditional metro ticketing systems often require passengers to purchase tickets manually or interact with ticket counters and machines, which can result in queues, longer processing times, and inconvenience during peak hours.

The proposed **Metro Management System with Smart Card Integration** is designed to provide a convenient and effficient smart-card-based transportation management solution. The system alows passengers to register, obtain a smart card, recharge the card balance, enter and exit metro stations, and automatically deduct the appropriate fare based on the distance travelled.

The system maintains passenger, smart-card, station, journey, and transaction informtion in a **MySQL database**. The application is developed using **Core Java and JDBC**, providing database connectivity and reliable processing of metro-related operations.

---

## 2. Project Scope

The project focuses on developing a computerized metro management system that supports smart-card-based travel and fare processing.

The major activities covered by the system are:

- Passenger registration and login
- Passenger profile management
- Smart-card registration and issuance
- Smart-card balance management
- Smart-card recharge
- Metro station management
- Passenger entry processing
- Passenger exit processing
- Distance-based fare calculation
- Automatic fare deduction
- Journey record management
- Transaction record management
- Database-based data storage
- Input validation
- Exception handling
- Secure and consistent processing of passenger transactions

The system is implemented as a **command-line Core Java application** using **JDBC for database connectivity** and **MySQL for data storage**.

---

## 3. Target Users

### 3.1 Passengers

Passengers are the primary users of the system. They can perform the following operations:

- Register a new account
- Log in to the system
- Obtain/register a smart card
- Check smart-card balance
- Recharge the smart card
- Enter a metro station
- Exit from a metro station
- View journey history
- View transaction history

### 3.2 Administrators

Administrators are responsible for managing and maintaining metro-related information in the system.

Administrative operations may include:

- Managing metro stations
- Managing passenger records
- Managing smart-card records
- Monitoring journey information
- Managing transaction-related information
- Maintaining system data

---

## 4. High-Level Features

The proposed system provides the following major features:

1. **Passenger Management**  
   Registration, login, and management of passenger information.

2. **Administrator Management**  
   Management of stations, passenger records, cards, and system information.

3. **Smart-Card Management**  
   Registration, issuance, and management of passenger smart cards.

4. **Card Recharge**  
   Allows passengers to add funds to their smart-card balance.

5. **Station Management**  
   Maintains information about metro stations and their respective locations.

6. **Metro Entry Processing**  
   Records the passenger's entry station when the passenger begins a journey.

7. **Metro Exit Processing**  
   Records the exit station and completes the passenger's journey.

8. **Distance-Based Fare Calculation**  
   Calculates the fare according to the distance travelled between the entry and exit stations.

9. **Automatic Fare Deduction**  
   Automatically deducts the calculated fare from the passenger's smart-card balance.

10. **Journey History**  
    Maintains records of previous metro journeys made by passengers.

11. **Transaction History**  
    Stores recharge and fare deduction transactions for future reference.

12. **Input Validation**  
    Validates user input to prevent invalid or incomplete data from being processed.

13. **Exception Handling**  
    Handles database errors, invalid operations, insufficient balance, and other runtime exceptions appropriately.

---

## 5. Fare Calculation Model

The system follows a distance-based fare structure. The fare is automatically calculated according to the total distance travelled between the passenger's entry and exit stations.

| Travel Distance | Fare |
|-----------------|-----:|
| 0–5 km          | ₹10  |
| Above 5–10 km   | ₹20  |
| Above 10–20 km  | ₹30  |
| Above 20 km     | ₹40  |

### Fare Calculation Process

The fare calculation and deduction process follows these steps:

1. The passenger taps/enters the smart card at the entry station.
2. The system records the entry station and journey start time.
3. The passenger travels to the destination station.
4. At the exit station, the system identifies the exit station.
5. The distance between the entry and exit stations is determined.
6. The applicable fare is calculated using the defined fare structure.
7. The system verifies whether the smart card has sufficient balance.
8. The calculated fare is deducted automatically from the smart card.
9. The journey details are stored in the database.
10. The fare deduction is recorded as a transaction.

---

## 6. Technology Used

| Component | Technology |
|-----------|------------|
| Programming Language | Core Java |
| Database | MySQL |
| Database Connectivity | JDBC |
| Application Type | Command-Line Application |
| Development Approach | Object-Oriented Programming |
| Data Storage | Relational Database |

---

## 7. Expected Outcome

The proposed **Metro Management System with Smart Card Integration** aims to provide a simple and efficient solution for managing metro passenger journeys and smart-card transactions.

The system reduces the need for manual fare calculation and ticket processing by automating passenger entry, exit, distance calculation, fare deduction, and record management. By maintaining important information in a MySQL database, the system provides organized storage of passenger, card, journey, station, and transaction data.

Overall, the project demonstrates the practical implementation of **Core Java, Object-Oriented Programming, JDBC, MySQL database management, validation, exception handling, and automated fare processing** in a real-world transportation management scenario.
