# 📘 Day 12 — API Versioning

## 📌 Overview

API versioning allows backend systems to **evolve safely** without breaking existing clients.
Once an API is public, backward compatibility becomes critical.

---

## WHAT

### What is API Versioning?

API versioning is the practice of evolving APIs by introducing new versions while continuing to support existing clients.

### Why is it needed?

As systems grow, APIs change. Versioning allows new features to be added without breaking older clients that depend on existing API contracts.

---

## WHY

API versioning prevents:

* Mobile app crashes
* Breaking integrations
* Client-side failures
* Risky rollbacks

It enables multiple client versions to coexist safely.

---

## COMMON VERSIONING STRATEGIES

### URI Versioning (Most Common)

```
/api/v1/resource
/api/v2/resource
```

✅ Simple
✅ Easy to understand
❌ URL changes

---

### Header Versioning

```
Accept: application/vnd.school.v1+json
```

✅ Clean URLs
❌ Harder to debug

---

### Query Parameter Versioning

```
/resource?version=1
```

❌ Not recommended
❌ Poor caching support

---

## MY SAAS CONTEXT

### Attendance API Evolution

**v1**

```java
Attendance {
    studentIds;
    classId;
    timeStamp;
}
```

**v2**

```java
Attendance {
    studentIds;
    classId;
    timeStamp;
    markedBy;
}
```

Both versions must work simultaneously.

---

## TINY DIAGRAM

```
Client v1 → /api/v1 → Server
Client v2 → /api/v2 → Server
```

---

## ACTION

### Booking API Versions

**v1**

```java
Booking {
    name;
    email;
    phoneNo;
    seatNo;
}
```

**v2**

```java
Booking {
    name;
    email;
    phoneNo;
    seatNo;
    timeStamp;
    theatreName;
}
```

---

## REFLECTION

### Why is removing fields dangerous?

Old clients depend on existing fields. Removing fields breaks backward compatibility and causes client failures.

### Which versioning strategy would you choose and why?

URI versioning because it is simple, explicit, easy to debug, and widely adopted in real-world systems.

---

## 3–3–1 SUMMARY

### 3 Key Concepts

1. APIs evolve over time
2. Backward compatibility is critical
3. Versioning protects clients

### 3 Use Cases

1. Mobile applications
2. Public APIs
3. Third-party integrations

### 1 Example

Adding a new field in `/api/v2` while keeping `/api/v1` unchanged.
