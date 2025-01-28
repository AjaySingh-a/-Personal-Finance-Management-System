# Personal Finance Management System

## Overview
The **Personal Finance Management System** is a full-stack Java application that enables users to manage their personal finances effectively. Users can track income, expenses, and budgets, analyze financial data, and gain insights into their spending habits. The project uses Spring Boot for the backend, MySQL for the database, and optionally a frontend framework for the user interface.

---

## Features
- **User Authentication**: Secure login and registration.
- **Transaction Management**: Add, update, delete, and view transactions (income/expenses).
- **Budgeting**: Set budgets and track progress.
- **Analytics**: Generate reports and visualize financial data.
- **Category Management**: Classify transactions into predefined categories.
- **RESTful APIs**: Backend provides APIs for seamless integration.

---

## Technologies Used

### Backend
- Java (Spring Boot)
- Spring Data JPA
- Hibernate
- MySQL

### Frontend (Optional)
- HTML/CSS (for basic UI)
- React.js, Angular, or Vue.js (for advanced UI)

### Tools
- IntelliJ IDEA / Eclipse
- Postman (API testing)
- MySQL Workbench (Database management)
- Maven (Build tool)

---

## Prerequisites
- JDK 17 or later
- Maven 3.6+
- MySQL 8.0+
- IDE (IntelliJ IDEA, Eclipse, or any preferred IDE)
- Postman (for testing APIs)

---

## Installation and Setup

### 1. Clone the Repository
```bash
$ git clone https://github.com/your-username/personal-finance-management.git
$ cd personal-finance-management
```

### 2. Configure the Database
- Create a database named `finance_management` in MySQL.
- Update `application.properties` with your MySQL credentials:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/finance_management
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

### 3. Run the Application
- Build and run the application using Maven:

```bash
$ mvn spring-boot:run
```

- Access the application:
  - API Endpoints: `http://localhost:8080`
  - Frontend (if integrated): `http://localhost:3000`

---

## Project Structure
```
|-- src
    |-- main
        |-- java
            |-- com.example.finance
                |-- controller
                    |-- FinanceController.java
                |-- entity
                    |-- Transaction.java
                    |-- User.java
                |-- repository
                    |-- TransactionRepository.java
                    |-- UserRepository.java
                |-- service
                    |-- TransactionService.java
        |-- resources
            |-- application.properties
            |-- static
            |-- templates
```

### Key Files
1. **Transaction.java**: Entity representing financial transactions.
2. **User.java**: Entity for user details and authentication.
3. **FinanceController.java**: Handles all API requests.
4. **TransactionRepository.java**: Repository for transaction CRUD operations.
5. **TransactionService.java**: Business logic for transactions.
6. **application.properties**: Configuration file for database and other properties.

---

## API Endpoints

### Transaction APIs
1. **Get Transactions for a User**
   - **GET** `/api/transactions/{userId}`
   - Response:
     ```json
     [
       {
         "id": 1,
         "category": "Food",
         "amount": 500.00,
         "type": "expense",
         "date": "2025-01-01",
         "userId": 1
       }
     ]
     ```

2. **Add a Transaction**
   - **POST** `/api/transactions`
   - Request Body:
     ```json
     {
       "category": "Entertainment",
       "amount": 100.00,
       "type": "expense",
       "date": "2025-01-18",
       "userId": 1
     }
     ```

3. **Update a Transaction** (To be implemented)

4. **Delete a Transaction** (To be implemented)

---

## Testing
1. **API Testing**:
   - Use Postman or curl to test the endpoints.

2. **Database Validation**:
   - Open MySQL Workbench and query the `transactions` table to verify data insertion:
     ```sql
     SELECT * FROM transactions;
     ```

---

## Future Enhancements
- Add user authentication using Spring Security.
- Implement advanced analytics with charts.
- Create a frontend using React.js or Angular.
- Integrate payment gateways for income tracking.
- Add multi-currency support.

---

## Contribution
Contributions are welcome! Feel free to fork the repository and submit pull requests.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

