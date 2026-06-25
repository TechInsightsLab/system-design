# Rate Limit:

---

Rate Limiting is a **traffic control mechanism that restricts the number of requests** a client, user, API key, IP address, service, or tenant can make within a specified time period to protect system resources, ensure fair usage, maintain performance, improve availability, and control operational costs.

### Example:

```
Policy:
100 requests/minute per user

User sends:
95 requests → Allowed

User sends:
101st request → Rejected (HTTP 429 Too Many Requests)
```

## Rate limiting is not just for blocking users.

✅ Protect downstream systems (Database, Redis, Kafka, Third-Party APIs).

✅ Prevent abuse and bot traffic.

✅ Ensure fair resource sharing among users and tenants.

✅ Handle traffic spikes gracefully.

✅ Prevent cascading failures.

✅ Control cloud infrastructure costs.

✅ Enforce service-level agreements (SLAs).

