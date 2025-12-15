# 📘 **Day 8 — Database Isolation Levels**

## 3–3–1 SUMMARY

### **3 Key Concepts**

1. Isolation controls how concurrent transactions interact.
2. Higher isolation prevents more anomalies but reduces performance.
3. Isolation levels are trade-offs between correctness and concurrency.

### **3 Real-World Use Cases**

1. Fee payments require high isolation.
2. Attendance updates need consistent reads.
3. Browsing data can tolerate lower isolation.

### **1 Tiny Example**

Two teachers updating marks at the same time should not corrupt student data.

---

## WHAT

### What is Isolation?

Isolation defines how much one transaction can see the intermediate state of another concurrent transaction.

### What are Isolation Levels?

* **Read Uncommitted**: Allows dirty reads, non-repeatable reads, and phantom reads.
* **Read Committed**: Prevents dirty reads; allows non-repeatable and phantom reads.
* **Repeatable Read**: Prevents dirty and non-repeatable reads; phantom reads may occur.
* **Serializable**: Prevents dirty reads, non-repeatable reads, and phantom reads.

---

## WHY

Databases need isolation to prevent data anomalies caused by concurrent transactions and to ensure data correctness.

---

## MY SAAS CONTEXT

* **Attendance data** → Repeatable Read / Serializable
* **Fee payments** → Serializable
* **Browsing data** → Read Committed

---

## DIAGRAM / FLOW

```
Tx1 and Tx2 running concurrently

Lower isolation  → More visibility
Higher isolation → Less visibility

Read Uncommitted → No protection
Read Committed   → Prevents dirty reads
Repeatable Read  → Prevents dirty & non-repeatable reads
Serializable     → Prevents all anomalies
```

---

## ACTION

* **Serializable**: Fee payment transactions
* **Read Committed**: Browsing list in booking systems

---

## REFLECTION

* **Why is Serializable slower?**
  Because it enforces strict transaction ordering or locking, reducing concurrency.

* **Why don’t we always use the highest isolation?**
  Because higher isolation reduces performance and throughput, which many real-time systems cannot afford.

---

## KEY TAKEAWAYS

* Isolation prevents concurrency bugs.
* Higher isolation increases safety but lowers performance.
* Most systems choose isolation levels per operation.

---
