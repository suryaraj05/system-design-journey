# 📘 Day 11 — REST API Design

## 📌 Overview

REST API Design defines how clients interact with backend resources in a **predictable, scalable, and maintainable** way using standard HTTP principles.
APIs act as **contracts** between clients and servers.

---

## WHAT

### What is REST API Design?

REST API design is about structuring APIs around **resources**, using HTTP methods to represent actions, and returning meaningful responses.

### What problem does it solve?

* Prevents overloading endpoints
* Enforces clarity between read/write operations
* Standardizes communication using HTTP methods and status codes

---

## WHY

Real systems need well-designed APIs because APIs are the **primary interface** between users and backend systems.
Good API design improves:

* Maintainability
* Scalability
* Developer experience
* User experience

---

## CORE REST PRINCIPLES

### 1️⃣ Resource-Based URLs

URLs represent **nouns**, not actions.

❌ `/getUserDetails`
✅ `/users/{id}`

---

### 2️⃣ Correct HTTP Methods

| Method | Purpose          |
| ------ | ---------------- |
| GET    | Retrieve data    |
| POST   | Create resource  |
| PUT    | Replace resource |
| PATCH  | Partially update |
| DELETE | Remove resource  |

---

### 3️⃣ Statelessness

* Each request contains all required data
* Server does not store client session state

**Benefits:**

* Horizontal scalability
* Easier load balancing
* Fault tolerance

---

### 4️⃣ Meaningful Status Codes

APIs must return truthful status codes.

| Code | Meaning               |
| ---- | --------------------- |
| 200  | OK                    |
| 201  | Created               |
| 400  | Bad Request           |
| 401  | Unauthorized          |
| 404  | Not Found             |
| 500  | Internal Server Error |

---

## MY SAAS CONTEXT (School Management System)

### Class Management APIs

```
POST   /classes
GET    /classes/{classId}
POST   /classes/{classId}/students
PATCH  /classes/{classId}/students/{studentId}
DELETE /classes/{classId}
DELETE /classes/{classId}/students/{studentId}
```

These APIs clearly represent:

* Resources
* Relationships
* Actions via HTTP methods

---

## TINY DIAGRAM

```
Client → HTTP → REST API → Service Layer → Database
```

---

## ACTION

### User Resource Design

```
POST   /users
GET    /users/{userId}
PUT    /users/{userId}
DELETE /users/{userId}
```

---

## REFLECTION

### Why are verbs in URLs bad?

URLs should represent **resources**, not actions. Actions are expressed using HTTP methods, not URL paths.

### Why is statelessness important?

Statelessness allows systems to scale horizontally and handle failures without maintaining session state on the server.

---

## COMMON MISTAKES TO AVOID

* Verb-based URLs
* Using POST for every operation
* Returning 200 for all responses
* Tightly coupling APIs to database entities

---

## KEY TAKEAWAYS

* REST APIs are contracts
* HTTP methods define behavior
* Stateless design enables scalability
* Clean APIs improve long-term maintainability

---

## 3–3–1 SUMMARY

### 3 Key Concepts

1. Resource-based design
2. HTTP method semantics
3. Stateless communication

### 3 Use Cases

1. CRUD operations
2. Client-server interaction
3. Scalable backend systems

### 1 Example

`GET /students/123` retrieves student data without server-side session state.

---
