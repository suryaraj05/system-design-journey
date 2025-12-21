# Day 13 — Pagination & Filtering

## 📌 Overview

Modern systems never return large datasets in a single response.
Pagination and filtering are essential techniques to **control data size, improve performance, and scale APIs safely**.

---

## 🔹 WHAT

### Pagination

Pagination means **splitting large datasets into smaller, fixed-size pages** instead of returning all records at once.

Example:

```
GET /students?page=0&size=50
```

Returns only 50 students instead of thousands.

---

### Filtering

Filtering means **returning only relevant data** based on conditions like class, date, or status.

Example:

```
GET /attendance?class=10A&date=2025-01-10
```

---

## 🔹 WHY

Pagination and filtering:

* Prevent database overload
* Reduce response size
* Improve API latency
* Protect systems from memory issues
* Provide better user experience (especially on mobile)

---

## 🔹 YOUR SAAS (School Management System)

Use pagination and filtering for:

* Student lists
* Attendance records
* Fee transactions
* Exam results

Example:

```
GET /attendance?page=0&size=30&class=9B&date=2025-01-10
```

---

## 🔹 REQUEST FLOW (TINY DIAGRAM)

```
Client → API → Database

Without pagination:
Database → 10,000 rows ❌

With pagination & filtering:
Database → 50 filtered rows ✅
```

---

## 🔹 EXAMPLE RESPONSE (Paginated)

```json
{
  "content": ["student1", "student2", "..."],
  "page": 0,
  "size": 20,
  "totalPages": 50,
  "totalElements": 1000
}
```

---

## 🔹 ACTION (5 Minutes)

Design one paginated and filtered endpoint:

```
GET /students?page=1&size=25&class=10A&status=ACTIVE
```

* Pagination: page, size
* Filtering: class, status

---

## 🔹 REFLECTION

### What breaks without pagination?

* High memory usage
* Slow database queries
* API timeouts
* Poor frontend and mobile performance

### Where should pagination happen?

* **Always at the database level**
* Never fetch all rows and paginate in memory

---

## ⚠️ COMMON MISTAKES

❌ Returning all records
❌ No page size limit
❌ Pagination after fetching all data
❌ Filtering in backend memory

✅ Paginate in DB
✅ Filter in DB
✅ Set max page size (e.g. 100)

---

## 📚 KEY TAKEAWAY

> Pagination and filtering are **non-negotiable fundamentals** for scalable backend systems.

---

If you want, next we’ll do **Day 14 — Rate Limiting** in the **same clean GitHub-ready format**.
