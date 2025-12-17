# 📘 **Day 10 — Retry & Exponential Backoff**

## 3–3–1 SUMMARY

### **3 Key Concepts**

1. Retries handle temporary failures.
2. Exponential backoff prevents retry storms.
3. Retries must be limited and used carefully.

### **3 Real-World Use Cases**

1. Email and SMS delivery
2. External API calls
3. Cache refresh or read operations

### **1 Tiny Example**

If an email service times out, retry after increasing delays instead of retrying immediately.

---

## WHAT

### What is Retry?

Retry means attempting a failed operation again, assuming the failure is temporary.

### What is Exponential Backoff?

Exponential backoff means waiting progressively longer after each retry instead of retrying immediately.

---

## WHY

Immediate retries can overwhelm a failing service. Exponential backoff gives the service time to recover and prevents retry storms.

---

## MY SAAS CONTEXT

Retry with backoff should be applied to:

* Email sending
* SMS delivery
* Fetching latest notices
* External API calls

---

## DIAGRAM / FLOW

```
Request → Fail → Retry → Wait → Retry → Success

Retry 1 → wait 1s
Retry 2 → wait 2s
Retry 3 → wait 4s
```

---

## ACTION

### Safe to Retry

* Fetching notices
* Email sending (idempotent)
* External API reads

### NOT Safe to Retry

* Creating bookings
* Charging payments
* Core database writes without idempotency

---

## REFLECTION

### What happens if retries have no backoff?

Immediate retries cause retry storms, resource exhaustion, and make recovery impossible.

### Why should retries be limited?

Unlimited retries overwhelm services and can cause system-wide failures.

---

## KEY TAKEAWAYS

* Retries handle temporary failures.
* Backoff prevents retry storms.
* Not all operations are safe to retry.
* Retry and circuit breaker should be used together.

---
