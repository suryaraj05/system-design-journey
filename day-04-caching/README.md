

# 📘 DAY 4 — CACHING

## WHAT

Caching stores frequently accessed data in fast in-memory storage (like Redis).

---

## WHY

Databases are slow compared to memory. Caching reduces latency and DB load.

---

## REAL-WORLD USE

Used for sessions, user profiles, feeds, configuration data.

---

## MY SAAS CONTEXT

Cache student attendance, timetable, and results for faster access.

---

## DIAGRAM / FLOW

```
Client → Backend → Cache → DB
Cache Hit → Fast Response
Cache Miss → DB → Cache → Response
```

---

## KEY TAKEAWAYS

* Cache is faster than DB
* TTL prevents stale data
* Cache-aside pattern is common

---
