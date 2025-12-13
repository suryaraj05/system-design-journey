

# 📘 DAY 6 — CAP THEOREM

## WHAT

CAP theorem states that a distributed system can guarantee only **two** of:

* Consistency
* Availability
* Partition Tolerance

---

## WHY

Network failures are inevitable, forcing systems to trade between correctness and uptime.

---

## REAL-WORLD USE

Systems choose CP or AP depending on business needs.

---

## MY SAAS CONTEXT

* CP: Attendance, Marks, Payments
* AP: Notifications, Timetable

---

## DIAGRAM / FLOW

```
Node A   ❌   Node B
Choose: Consistency OR Availability
```

---

## KEY TAKEAWAYS

* Partition tolerance is mandatory
* CA systems don’t exist in distributed systems
* Trade-offs depend on use case

---
