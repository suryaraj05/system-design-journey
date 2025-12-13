
# 📘 DAY 1 — SCALING (Vertical vs Horizontal)

## WHAT

Scalability is the ability of a system to handle increased load (users, requests, data) without crashing or slowing down.
Scaling can be done **vertically** or **horizontally**.

* **Vertical Scaling**: Increase resources of a single machine (CPU, RAM, disk).
* **Horizontal Scaling**: Add more machines and distribute load among them.

---

## WHY

User traffic grows unpredictably. A system must scale to avoid downtime during peak usage.

---

## REAL-WORLD USE

* Vertical scaling is quick but limited.
* Horizontal scaling is complex but supports large-scale systems.

---

## MY SAAS CONTEXT

For a school management system with thousands of students, horizontal scaling is preferred to handle concurrent access during exams or result announcements.

---

## DIAGRAM / FLOW

```
Vertical:
Client → Server (bigger & bigger)

Horizontal:
Client → Load Balancer → Server1, Server2, Server3
```

---

## KEY TAKEAWAYS

* Vertical scaling has hardware limits.
* Horizontal scaling is fault-tolerant.
* Modern systems prefer horizontal scaling.

---