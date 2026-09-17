# Metro Management System with Smart Card Integration

## 1. Abstract
The Metro Management System is a Core Java application designed to simplify metro operations and improve the passenger experience through smart cards. Passengers can register, obtain a smart card, recharge it, enter and exit stations, and automatically pay fares based on travel distance. The system stores passenger, card, station, journey and transaction information in MySQL.

## 2. Problem Statement
Traditional ticketing can create queues and repeated ticket purchases for daily users. Manual management of passenger journeys and fare collection can also increase processing time and errors. The proposed system introduces a smart-card based digital workflow for faster and more convenient metro travel.

## 3. Objectives
- Digitize passenger registration and card management.
- Reduce dependence on paper tickets.
- Automate fare calculation and balance deduction.
- Maintain journey and transaction records.
- Provide an easy desktop interface for users.

## 4. Scope
The prototype covers passenger accounts, smart cards, station data, recharge, entry/exit journeys and automatic fare calculation. Advanced real-world integrations such as NFC hardware, payment gateways and live train tracking are outside the prototype scope.

## 5. Technology
- Java 17+
- Core Java CLI
- JDBC
- MySQL 8
- OOP principles
- Exception handling and collections

## 6. System Modules
1. Authentication and registration
2. Smart card management
3. Recharge and transactions
4. Station management
5. Journey management
6. Fare calculation
7. Journey history

## 7. Working
A passenger logs in and gets an active smart card. At entry, the card is associated with the selected station. At exit, the system finds the open journey, calculates distance using station positions, determines fare using FareCalculator, checks balance, deducts the fare and closes the journey. A transaction record is created.

## 8. Fare Logic
0–5 km = ₹10
5–10 km = ₹20
10–20 km = ₹30
Above 20 km = ₹40

## 9. OOP Concepts
- Encapsulation: private fields with getters.
- Inheritance: Passenger and Admin extend User.
- Abstraction: User is abstract.
- Polymorphism: getRole() is overridden.
- Composition/association: journeys use cards and stations.
- Exception handling: ValidationException handles invalid operations.

## 10. Database Design
Tables: admins, passengers, stations, smart_cards, transactions, journeys.

## 11. Security Note
This academic prototype stores passwords as plain text for simplicity. A production system should use salted password hashing, stronger validation, role-based access control and secure payment/NFC integration.

## 12. Future Enhancements
- QR/NFC card readers
- Mobile application
- Online payment gateway
- Monthly passes
- Real-time train tracking
- Admin analytics
- Password hashing
- Cloud deployment

## 13. Conclusion
The project demonstrates how Core Java, Swing, JDBC and MySQL can be combined to create a practical transport-management application. Smart-card based fare processing makes the prototype suitable for daily metro users while providing a clear demonstration of object-oriented programming and database connectivity.


## Command-Line Executability

The primary entry point is `metro.Main`. The application is intentionally implemented as a terminal-based interface so it can be compiled and executed from a command prompt without any GUI-based setup. The repository includes `run.bat` and `run.sh` launchers, along with exact compilation and execution commands in the README.
