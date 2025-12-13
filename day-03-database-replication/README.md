
# 📘 DAY 3 — DATABASE REPLICATION

## WHAT

Replication means maintaining multiple copies of a database.

* **Primary (Master)**: Handles writes
* **Replica (Slave)**: Handles reads

---

## WHY

* Improves read performance
* Provides data backup
* Increases availability

---

## REAL-WORLD USE

Most production databases use primary–replica setups.

---

## MY SAAS CONTEXT

Student data reads go to replicas, while updates go to the primary database.

---

## DIAGRAM / FLOW

```
Writes → Primary DB
Reads  → Replica DBs
```

---

## KEY TAKEAWAYS

* Replicas are usually read-only
* Failover is possible
* Sync vs async replication trade-offs exist

---