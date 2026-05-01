---
layout: post
title: "TokoHP: Modern Full-Stack Smartphone E-Commerce"
date: 2026-02-08 20:00:00 +0700
categories: [projects, web-development]
tags: [javascript, full-stack, e-commerce, react, nodejs, express, mysql, tailwindcss]
author: aipunpratama
image: /assets/hp-ecommerce-banner.jpg
description: "A robust full-stack e-commerce web application for selling smartphones, featuring JWT authentication, role-based access, and a complete shopping cart system built with React and Express/MySQL."
---

<div align="center">

<a href="https://github.com/aipunpratama/hp-ecommerce" target="_blank">
  <img src="https://img.shields.io/badge/GitHub_Repo-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Repo">
</a>

<br><br>

<img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js">
<img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express">
<img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
<img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React">
<img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS">
<img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite">

</div>

---

## 📖 Project Overview

**TokoHP** is a fast, responsive, and secure full-stack e-commerce web application tailored specifically for selling smartphones. Built entirely with the JavaScript ecosystem (PERN/SERN stack variant using MySQL instead of NoSQL), this platform provides a seamless shopping experience for customers and a powerful management dashboard for administrators.

> *"Connecting gadget lovers with their dream smartphones through a fast, secure, and modern digital storefront."*

### 🎯 **Mission**
To design and develop a scalable relational-database e-commerce solution that handles everything from product browsing and cart management to secure user authentication and order processing.

---

## ✨ Key Features

### 🛍️ **Customer Experience**
- 📱 **Dynamic Product Catalog** - Browse a wide range of smartphones with search, filter, sort, and pagination capabilities.
- 🛒 **Smart Shopping Cart** - Add, remove, and adjust product quantities with real-time calculations.
- ⚡ **Direct Checkout** - "Buy Now" functionality for instant order processing.
- 🔐 **Secure Authentication** - User registration and login using JWT (JSON Web Tokens) with Refresh Token mechanics.
- 📋 **Order Tracking** - Customers can view their order history and track the current status of their deliveries.

### ⚙️ **Admin & Management (Role-Based Access)**
- 📊 **Product Management (CRUD)** - Admins can create, read, update, and delete product listings, complete with image uploads via **Multer**.
- 📦 **Order Management** - View all customer orders and update shipping/delivery statuses in real-time.
- 🛡️ **Advanced Security** - Built-in backend protections including Helmet, CORS, Rate Limiting, and Input Validation via **Joi**.

---

## 🛠️ Technology Stack

| Category               | Technology        | Purpose                                      |
| ---------------------- | ----------------- | -------------------------------------------- |
| **Frontend**           | React, Vite       | Fast, component-based interactive UI         |
| **Styling**            | Tailwind CSS      | Utility-first CSS for responsive design      |
| **HTTP Client**        | Axios             | API communication between client and server  |
| **Backend Framework**  | Node.js & Express | Server-side routing and RESTful API creation |
| **Database**           | MySQL 8.x         | Relational database for structured data      |
| **Authentication**     | JWT & Bcrypt      | Secure sessions and password hashing         |
| **Validation/Logging** | Joi & Winston     | Strict input validation and system logging   |

---

## 🏗️ Architecture & API Endpoints

### **System Architecture**
The project is structured as a clear separation of concerns between the client and server:
- **`frontend/`**: Contains the React application powered by Vite, using React Router for navigation and React Hot Toast for notifications.
- **`backend/`**: Houses the Express server, MySQL connection pools, authentication middleware, and RESTful API controllers.

### **Core REST API Routes**
The backend exposes several structured endpoints, secured via Role-Based Access Control (RBAC):
- **Auth:** `POST /api/auth/login`, `POST /api/auth/register`, `POST /api/auth/refresh`
- **Products:** `GET /api/products` (Public), `POST /api/products` (Admin Only)
- **Cart:** `GET /api/cart`, `POST /api/cart` (Customer Only)
- **Orders:** `POST /api/orders/checkout` (Customer), `PATCH /api/orders/:id/status` (Admin)

---

## 🚀 Installation & Setup

### **Prerequisites**
- Node.js v20.19+ or v22+
- MySQL 8.x (or XAMPP)
- Git

### **Setup Instructions**

**1. Setup Database**
```sql
# Open MySQL shell or phpMyAdmin
# Run the schema and seed files to create tables and dummy data
source backend/database/schema.sql;
source backend/database/seed.sql;
```

**2. Setup Backend**
```bash
cd backend
npm install
cp .env.example .env  # Edit with your MySQL database credentials
npm run dev
```

**3. Setup Frontend**
```bash
cd frontend
npm install
npm run dev
```

*(Demo Accounts: Login as `admin@tokoHP.com` or `budi@email.com` to explore the different role perspectives!)*

---

## 📊 Project Highlights

<div align="center">

<img src="https://img.shields.io/badge/Status-Completed-success?style=flat-square" alt="Status">
<img src="https://img.shields.io/badge/Code-99%25_JavaScript-yellow?style=flat-square" alt="JavaScript">
<img src="https://img.shields.io/badge/Type-Full_Stack-blue?style=flat-square" alt="Full Stack">

</div>

### **Key Achievements**
- ✅ **Relational Data Mastery** - Shifted from typical NoSQL MERN stacks to use a robust **MySQL** relational database design, handling complex joins between users, carts, products, and orders.
- ✅ **Secure Authentication Flow** - Implemented a highly secure token-based authentication system using both Access Tokens and Refresh Tokens.
- ✅ **Modern Tooling** - Leveraged Vite for blazing-fast frontend builds and Tailwind CSS for rapid, responsive UI development.

---

## 💡 Conclusion

Building the **TokoHP** app was a comprehensive exercise in modern full-stack development. By utilizing React alongside Express and MySQL, the project demonstrates how to structure a scalable, relational data-driven application. It perfectly simulates a real-world e-commerce workflow, from uploading product images as an admin to managing a secure checkout session as a customer.

---

### 🌐 Link Repo

**Developed with ❤️ by [aipunpratama](https://github.com/aipunpratama)**

<div align="center">

<a href="https://github.com/aipunpratama/hp-ecommerce">
  <img src="https://img.shields.io/badge/View_on_GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>
</div>

---

<div align="center">
<sub>🛒 Ready to shop? Don't forget to give the repository a star if you liked this project! ⭐</sub>
</div>