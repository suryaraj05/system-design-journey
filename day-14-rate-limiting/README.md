# Day 14 — Rate Limiting

## 📌 Overview

Rate limiting is a critical protection mechanism that controls how many requests a client can make within a given time window. It ensures system stability, fairness, and availability.

---

## WHAT

### What is Rate Limiting?

Rate limiting controls the number of requests a user or client can make within a defined time window.

Example:

> 100 requests per minute per user

If exceeded, further requests are blocked.

---

## WHY

Rate limiting protects systems from abuse, prevents resource exhaustion, ensures fair usage, maintains availability, and reduces the risk of DoS attacks.

---

## MY SAAS CONTEXT

In a school management system, rate limiting should be applied to:

* Login endpoints
* OTP requests
* Result fetching APIs
* Public-facing APIs

Example:

```
POST /login → heavily rate-limited
GET /results → lightly rate-limited
```

---

## TINY DIAGRAM

```
Client → Rate Limiter → API
```

---

## ACTION

### Heavily Rate-Limited Endpoint

* Login endpoint on public domains

### Lightly Rate-Limited Endpoint

* Product listing in an e-commerce system
* Result fetching APIs

---

## REFLECTION

### What breaks without rate limiting?

* Backend resources get exhausted
* APIs become unavailable
* System becomes vulnerable to abuse and DoS attacks

### Why is HTTP 429 important?

HTTP 429 (Too Many Requests) clearly informs clients that the request limit has been exceeded and prevents backend resource exhaustion.

---

## KEY TAKEAWAYS

* Rate limiting protects system stability
* Not all endpoints need the same limits
* 429 is part of a healthy API contract
* Essential for public-facing systems
