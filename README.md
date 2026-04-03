# 💰 Finance Backend System

## 📌 Overview

This project is a backend system for a finance dashboard that manages financial records, user roles, and summary analytics.

It demonstrates API design, role-based access control, and data aggregation — key backend concepts used in fintech systems.

---

## 🚀 Tech Stack

* Node.js
* Express.js
* SQLite (for simplicity and reliability)

---

## 📁 Folder Explanation

* controllers → business logic
* routes → API endpoints
* middleware → role-based access

---

## 🧠 Design Decisions

* SQLite used for simplicity and zero setup
* Middleware used for role-based access control
* Aggregation queries used for dashboard insights

---

## ⚙️ Setup Instructions

1. Clone the repository

2. Install dependencies:
   npm install

3. Start the server:
   node server.js

Server runs at:
http://localhost:4000

---

## 👤 Roles & Permissions

| Role    | Access                               |
| ------- | ------------------------------------ |
| Viewer  | Read-only access to records          |
| Analyst | View records + summary analytics     |
| Admin   | Full access (create, update, delete) |

Pass role in request header:
role: admin / analyst / viewer

---

## 📡 API Endpoints

### Users

* POST /users → Create user
* GET /users → Get all users

### Records

* POST /records → Create record (Admin only)
* GET /records → Get records (All roles)
* PUT /records/:id → Update record (Admin only)
* DELETE /records/:id → Delete record (Admin only)

### Summary

* GET /summary → Total income, expenses, balance (Analyst/Admin)
* GET /summary/category → Category-wise totals

---

## 🧪 Example Request

### Create Record

POST /records

Headers:
role: admin

Body:
{
"amount": 5000,
"type": "income",
"category": "salary",
"date": "2026-04-04",
"notes": "April salary"
}

---

## 📊 Example Response

{
"total_income": 5000,
"total_expense": 2000,
"net_balance": 3000
}

---

## ⚡ Quick Testing Guide

1. Create a user (POST /users)
2. Add records using role: admin
3. Fetch records using role: viewer
4. Access summary using role: analyst

---

## 📊 Features Implemented

* Role-based access control using middleware
* Financial records CRUD operations
* Aggregated summary APIs
* Input validation and error handling
* Lightweight SQLite database for easy setup

---

## 💡 Notes

SQLite is used to ensure the project runs without external dependencies.

In production systems, PostgreSQL or MySQL would be preferred for scalability and consistency.

---

## 🏁 Conclusion

This project demonstrates clean backend architecture, role-based authorization, and financial data processing aligned with real-world fintech backend systems.
