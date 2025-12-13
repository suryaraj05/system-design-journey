
# 📘 DAY 5 — MESSAGE QUEUES

## WHAT

A message queue enables asynchronous communication between services.

* **Producer** sends messages
* **Queue** stores messages
* **Consumer** processes messages

---

## WHY

Async processing prevents blocking and improves scalability.

---

## REAL-WORLD USE

Used for emails, notifications, background jobs.

---

## MY SAAS CONTEXT

Attendance service sends events; notification service processes them asynchronously.

---

## DIAGRAM / FLOW

```
Producer → Queue → Consumer
```

---

## KEY TAKEAWAYS

* Decouples services
* Handles traffic spikes
* Supports retries and scaling

---