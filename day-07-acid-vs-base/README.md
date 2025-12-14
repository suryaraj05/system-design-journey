# 📘 **Day 7 — ACID vs BASE (Consistency Models)**

## 3–3–1 SUMMARY

### **3 Key Concepts**

1. **ACID** provides strong consistency guarantees for transactional systems.
2. **BASE** provides high availability and scalability using eventual consistency.
3. Real-world systems use **trade-offs**, often mixing ACID and BASE.

### **3 Real-World Use Cases**

1. **ACID**: Banking systems, payment processing, seat reservation checkout.
2. **BASE**: News feeds, notifications, browsing/search results.
3. **Hybrid**: E-commerce platforms use ACID for orders and BASE for browsing.

### **1 Tiny Example**

A fee payment transaction must either fully succeed or fully fail (ACID),
while a notification about the payment can be delayed and eventually consistent (BASE).

---

## WHAT

**ACID** and **BASE** are consistency models that define how databases handle correctness, availability, and scalability.

### ACID (Strong Consistency Model)

* **Atomicity**: A transaction is all-or-nothing.
* **Consistency**: Data moves from one valid state to another.
* **Isolation**: Concurrent transactions do not interfere.
* **Durability**: Committed data survives system crashes.

### BASE (Eventual Consistency Model)

* **Basically Available**: System remains responsive.
* **Soft State**: Data may temporarily change.
* **Eventual Consistency**: Data becomes consistent over time.

---

## WHY

Distributed systems often prefer **BASE** because high availability and scalability are more important than immediate consistency for many operations.

---

## REAL-WORLD USE

* **ACID** ensures correctness where errors are unacceptable.
* **BASE** enables systems to stay available under heavy load.

---

## MY SAAS CONTEXT

* **ACID**: Attendance records, exam marks, fee payments.
* **BASE**: Notices, timetable, notifications.

---

## DIAGRAM / FLOW

```
ACID → Strong Consistency → Safer but Slower
BASE → Eventual Consistency → Faster and Scalable
```

---

## KEY TAKEAWAYS

* ACID prioritizes correctness and safety.
* BASE prioritizes availability and scalability.
* Eventual consistency is a deliberate design choice.
* Most systems use a hybrid approach.

---

## ACTION

**ACID Systems**

* Banking transactions
* Seat reservation checkout

**BASE Systems**

* News platforms
* Search and browsing results

---

## REFLECTION

* **Why is eventual consistency acceptable sometimes?**
  When correctness is not critical and availability matters more than freshness.

* **When is ACID mandatory?**
  When incorrect data can cause financial loss or system corruption.

---
