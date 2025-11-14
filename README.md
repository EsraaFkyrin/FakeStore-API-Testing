# Fake Store API – E-Commerce Testing Suite

## Project Overview

A **production-grade Postman collection** demonstrating **enterprise-level API testing** on the [Fake Store API](https://fakestoreapi.com) – a realistic e-commerce platform.

This suite simulates a **complete user journey**:
- Authentication with JWT
- Product browsing
- Cart management (Add, Update, Delete)
- Request chaining with dynamic IDs & tokens

---

## Key Features

| Feature | Implementation |
|--------|----------------|
| **JWT Authentication** | `POST /auth/login` → `{{auth_token}}` |
| **Request Chaining** | `{{cart_id}}` for cart operations |
| **Dynamic Data** | Environment variables for `username`, `password` |
| **Automated Validation** | 25+ `pm.test` assertions |
| **Console Debugging** | Full visibility with `console.log` |
| **Fail-Fast Logic** | Pre-request scripts prevent invalid runs |

---

## Test Cases Summary

| # | Test Case | Method | Endpoint | Expected | Status |
|---|----------|--------|----------|----------|--------|
| 1 | Retrieve all products | `GET` | `/products` | 200 + 20 items | PASS |
| 2 | Get single product | `GET` | `/products/1` | 200 + valid schema | PASS |
| 3 | User login | `POST` | `/auth/login` | 200 + JWT token | PASS |
| 4 | Add product to cart | `POST` | `/carts` | 200 + cart ID | PASS |
| 5 | Retrieve user cart | `GET` | `/carts/5` | 200 + correct userId | PASS |
| 6 | Update cart quantity | `PUT` | `/carts/:id` | 200 + quantity = 10 | PASS |
| 7 | Delete cart | `DELETE` | `/carts/:id` | 200 + `{}` | PASS |

> **Total Tests: 25** | **Pass Rate: 100%** | **Avg. Response Time: 180ms**

---

## Project Structure
FakeStore-API-Testing/
├── collection/
│   └── FakeStore_Professional.postman_collection.json
├── environment/
│   └── FakeStore_Env.postman_environment.json
├── reports/
│   └── API_Testing_Report.pdf
├── screenshots/
│   └── passed_tests.png
├── README.md
├── LICENSE
└── .gitignore


---

## How to Run

1. **Import** the collection and environment into Postman
2. **Select** `FakeStore Environment`
3. **Run requests in order**:
   GET All Products
   GET Single Product
   POST Login → Save Token
   POST Add to Cart → Save cart_id
   GET User Cart
   PUT Update Cart
   DELETE Remove Cart

