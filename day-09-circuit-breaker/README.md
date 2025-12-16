# 📘 **Day 9 — Circuit Breaker Pattern**

## 3–3–1 SUMMARY

### **3 Key Concepts**

1. Circuit breakers prevent cascading failures in distributed systems.
2. They stop calling failing services and allow recovery.
3. Fast failure is better than slow failure.

### **3 Real-World Use Cases**

1. Payment gateways
2. Email and SMS services
3. External third-party APIs

### **1 Tiny Example**

Attendance is saved successfully, but the email notification fails without affecting the main operation.

---

## WHAT

### What is a Circuit Breaker?

A circuit breaker is a protective mechanism that stops calls to a failing service to prevent cascading failures.

### Why does it exist?

It prevents systems from repeatedly calling slow or unavailable services, which can exhaust resources and crash the system.

---

## WHY

Circuit breakers prevent **cascading failures**, where one failing service causes multiple dependent services to fail.

---

## MY SAAS CONTEXT

Circuit breakers should be applied to:

* Email services
* SMS gateways
* Payment gateways
* External APIs

Core business logic (marks, attendance, fees) should remain strongly consistent.

---

## DIAGRAM / FLOW

```
Service A → Circuit Breaker → Service B

If failures exceed threshold:
Circuit opens → calls blocked → fast failure
```

---

## ACTION

* **External dependency**: Payment gateway
* **Internal dependency**: Email or SMS service

---

## REFLECTION

### What happens if we don’t use circuit breakers?

A failing service gets called repeatedly, causing thread exhaustion, timeouts, and eventually a system-wide crash.

### Why is fast failure better than slow failure?

Fast failure avoids resource exhaustion, protects system stability, and allows dependent services time to recover.

---

## KEY TAKEAWAYS

* Circuit breakers protect systems under failure.
* They isolate failures instead of spreading them.
* Recovery is as important as prevention.

---
