# Banking Management System — Hibernate Version

## 📌 Overview

This project is a simple **Banking Management System** implemented using **Hibernate ORM** with Oracle Database.
It demonstrates core Hibernate concepts such as:

* Entity mapping
* DTO–entity separation
* Sequence-based primary key generation
* Transaction management
* Dirty checking
* One-to-Many relationship mapping
* Fund transfer atomicity

The application supports account validation, balance retrieval, and secure fund transfer between accounts.

---

## 🏗 Architecture

The application follows a layered architecture:

```
Main → Service → DAO → Hibernate → Oracle DB
```

### Layers

* **DTO Layer**

  * `TransferBean` — carries transfer request data
* **Entity Layer**

  * `Account`
  * `Transfer`
* **DAO Layer**

  * Handles persistence operations via Hibernate Session API
* **Service Layer**

  * Contains business validation and orchestration
* **Utility Layer**

  * `HibernateUtil` — SessionFactory management

---

## 🗄 Database Schema

### ACCOUNT_TBL

| Column         | Type              |
| -------------- | ----------------- |
| ACCOUNT_NUMBER | VARCHAR2(10) (PK) |
| CUSTOMER_NAME  | VARCHAR2(15)      |
| BALANCE        | NUMBER(10,2)      |

---

### TRANSFER_TBL

| Column                     | Type           |
| -------------------------- | -------------- |
| TRANSACTION_ID             | NUMBER(4) (PK) |
| ACCOUNT_NUMBER             | VARCHAR2(10)   |
| BENEFICIARY_ACCOUNT_NUMBER | VARCHAR2(10)   |
| TRANSACTION_DATE           | DATE           |
| TRANSACTION_AMOUNT         | NUMBER(10,2)   |

---

### Sequence

```
transactionID_seq1
```

Used for auto-generating transaction IDs.

---

## ⚙ Technologies Used

* Java
* Hibernate ORM 6.x
* Oracle XE
* Maven
* JPA Annotations

---

## 🔑 Key Hibernate Concepts Implemented

* Annotation-based entity mapping
* Oracle sequence mapping using `@SequenceGenerator`
* Lazy loading relationship (`@OneToMany`, `@ManyToOne`)
* Transaction management with commit/rollback
* Hibernate dirty checking for balance updates
* DTO to entity transformation

---

## 🚀 Features

* Account validation
* Balance retrieval
* Atomic fund transfer
* Transaction history recording
* Automatic transaction ID generation
* Precision-safe monetary operations using BigDecimal

---

## ▶ How to Run

1. Create database tables and sequence in Oracle.
2. Configure database credentials in `hibernate.cfg.xml`.
3. Build the project using Maven.
4. Run `Main.java`.

---

## ⚠ Notes

* Schema auto-update is disabled to preserve existing tables.
* BigDecimal is used for monetary accuracy.
* TransferBean acts as DTO and is not mapped as entity.

---

## 🎯 Learning Outcomes

This project demonstrates:

* Migration from JDBC to Hibernate
* Proper separation of DTO and Entity layers
* Hibernate session lifecycle management
* Realistic fund transfer workflow
* Oracle sequence integration with Hibernate

---

## 📬 Future Improvements

* Optimistic locking for concurrency control
* Transaction history retrieval via HQL
* REST API integration
* Spring Boot migration
* Pessimistic locking for banking-grade safety

---
## output
<img width="1607" height="523" alt="image" src="https://github.com/user-attachments/assets/5e583928-da4d-41f9-ab91-464fa469cad3" />
<img width="695" height="377" alt="image" src="https://github.com/user-attachments/assets/56f34738-aaeb-4b47-9e18-e79ce25df98b" />


**Author:** Sham
**Purpose:** Academic / Learning Project
