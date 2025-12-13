

# 📘 DAY 2 — LOAD BALANCING

## WHAT

A load balancer distributes incoming traffic across multiple servers to prevent overload.

Common algorithms:

* Round Robin
* Least Connections
* Weighted Distribution

---

## WHY

Without load balancing, a single server becomes a bottleneck and crashes under high traffic.

---

## REAL-WORLD USE

Used in all large-scale applications like Netflix, Amazon, Google.

---

## MY SAAS CONTEXT

During peak times (attendance marking, results), load balancer routes users to healthy servers.

---

## DIAGRAM / FLOW

```
Client → Load Balancer → Server1 | Server2 | Server3
```

---

## KEY TAKEAWAYS

* Improves availability
* Enables horizontal scaling
* Supports health checks

---
