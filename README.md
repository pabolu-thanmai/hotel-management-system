# Hotel Management System (Java)

## Overview
This is a Java-based console Hotel Management System developed to apply core Java and OOP concepts in a practical scenario.  
The application manages room booking, availability, food ordering, checkout, and data persistence.

The project was initially implemented as a single-file application and later refactored into a structured format with clear separation of responsibilities.

---

## Features
- Display room details by category
- Check room availability
- Book single or double rooms
- Order food for booked rooms
- Checkout and bill generation
- Persist hotel state across program runs using serialization

---

## Project Structure
src/
├── model/
│ ├── Food.java
│ ├── Singleroom.java
│ ├── Doubleroom.java
│ └── NotAvailable.java
├── service/
│ ├── holder.java
│ ├── Hotel.java
│ └── write.java
└── HotelApp.java


---

## Core Concepts Used
- Object-Oriented Programming (OOP)
- Encapsulation and abstraction
- Custom exception handling
- Java Serialization for persistence
- Multithreading for non-blocking file I/O
- File handling using ObjectInputStream and ObjectOutputStream

---

## How the System Works
- A single `holder` object maintains the complete hotel state.
- All operations update this shared state through the `Hotel` service class.
- The state is serialized to a file (`backup`) on exit and restored on the next run.
- Food orders are accumulated per room and billed during checkout.

---

## How to Run
### Compile
javac src/model/*.java src/service/*.java src/HotelApp.java

### Run
java -cp src HotelApp
