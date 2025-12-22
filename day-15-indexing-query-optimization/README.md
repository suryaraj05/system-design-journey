# Day 15 — Database Indexing & Query Optimization

*(Intermediate System Design)*

---

## 📌 Overview

As systems scale, database performance often becomes the first bottleneck.
Database indexing and query optimization are essential techniques to keep query latency predictable and prevent backend slowdowns under growing load.

---

## 1️⃣ Problem (Real-World Pain)

As data grows, database queries that were once fast begin to slow down significantly. Queries start scanning more rows, increasing CPU usage, disk I/O, and response time. Under load, slow queries pile up, causing timeouts and eventually degrading the entire backend system.

---

## 2️⃣ Naive Approach (And Why It Fails)

A naive system assumes the database is fast enough and executes queries without indexes or optimization. This works when tables are small, but as the number of rows increases, queries perform full table scans. Over time, latency increases linearly with data size, making the database a performance bottleneck.

---

## 3️⃣ Correct Design (Mental Model)

The correct approach is to design queries based on access patterns and create indexes only where they significantly reduce the search space. Indexes allow the database to locate rows efficiently, while optimized queries ensure minimal data is read and processed. Together, they keep read performance fast and predictable as data scales.

---

## 4️⃣ Trade-offs (Nothing Is Free)

* Faster read performance
* Slower write operations due to index maintenance
* Additional storage usage for indexes
* Increased complexity in schema and query planning

> Indexing improves reads at the cost of writes.

---

## 5️⃣ Failure Modes (What Can Go Wrong)

* **Over-indexing** slows down inserts and updates and bloats storage
* **Under-indexing** causes slow queries and full table scans
* **Wrong indexes** exist but are never used due to query patterns
* **Poorly written queries** negate the benefits of indexing

---

## 6️⃣ My SaaS Mapping (School Management System)

In a school management system, most queries are based on student, class, date, and subject. Indexing columns such as:

* `student_id`
* `class_id`
* `attendance_date`
* `subject_id`

allows fast retrieval of attendance, results, and reports even under heavy daily query load.

---

## 🛑 Stop Point (Very Important)

Do not dive into composite indexes, index internals, query planners, or database-specific tuning yet. The focus here is understanding **why** indexing matters and **where** to apply it — not how databases implement it internally.

---

## ✅ One-Line Takeaway

Database indexing and query optimization keep read performance fast and predictable by avoiding full table scans as data grows.