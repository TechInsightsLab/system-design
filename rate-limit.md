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

---

## Interview Questions:


### Level 1: Basic Questions
**Q1:** What is Rate Limiting?

**Q2:** Why do we need Rate Limiting?

**Q3:** What problems does Rate Limiting solve?

**Q4:** What happens if Rate Limiting is not implemented?

**Q5:** Difference between:
  - Rate Limiting
  - Throttling
  - Load Balancing
  - Autoscaling

**Q6:** What is HTTP 429?

**Q7:** What information can be used for Rate Limiting?

Examples:

```
IP
UserId
API Key
TenantId
DeviceId
Endpoint
```


### Level 2: Placement Questions
**Q8:** Where would you place the Rate Limiter?

```
CDN
WAF
Load Balancer
API Gateway
Application
Service Mesh
Database
```

**Q9:** Can we have multiple rate limiters?

**Q10:** Why place Rate Limiting at API Gateway instead of Application?

**Q11:** Why not put Rate Limiting only at Database?

**Q12:** How do you protect internal microservices?



### Level 3: Algorithm Questions
**Q13:** Explain Fixed Window.

**Q14:** Explain Sliding Window Log.

**Q15:** Explain Sliding Window Counter.

**Q16:** Explain Token Bucket.

**Q17:** Explain Leaky Bucket.

**Q18:** Which algorithm would you choose and why?

**Q19:** Which algorithm supports bursts?

**Q20:** Which algorithm is most accurate?



### Level 4: Distributed System Questions
**Q22:** How would you implement Rate Limiting in a single server?

**Q23:** How would you implement Rate Limiting in a distributed environment?

**Q24:** Why is local memory insufficient?

**Q25:** Why use Redis?

**Q26:** What would you store in Redis?

**Q27:** How would Redis key design look?

```
Example:

rate:user123
```

**Q28:** How do you handle race conditions?

**Q29:** Why use Redis INCR?

**Q30:** Why use Lua Scripts?

**Q31:** How do you scale Redis?

**Q32:** What if Redis becomes bottleneck?


### Level 5: Capacity Planning Questions

**Q33:** How should Rate Limiting be configured?

```
Database supports: 100K TPS
```

```
Application supports: 500K TPS
```

**Q34:** How do you determine the correct limit?

**Q35:** Can all APIs have same limit?

**Q36:** How would you design limits for:

```
Login
Search
Payment
```


### Level 6: Multi-Tenant Questions
**Q37:** How would you implement:

```
Free User
Premium User
Enterprise User
```

limits?

**Q38:** How do you prevent one tenant from consuming all resources?

**Q39:** Can a request be checked against multiple limits?

Example:
```
User
Tenant
IP
API
```

### Level 7: Failure Questions

**Q40:** What happens if Redis crashes?

**Q41:** Fail Open vs Fail Closed?

**Q42:** Which APIs should use Fail Open?

Example:

```
Search
Q43
```

Which APIs should use Fail Closed?

Example:

```
Login
Payment
```

**Q44:** What happens if Rate Limiter itself fails?

**Q45:** How do you monitor Rate Limiter health?


### Level 8: Bot Protection Questions

**Q46:** Why is IP-based Rate Limiting insufficient?

**Q47:** How do bots bypass IP Rate Limiting?

**Q48:** How do you stop rotating IP attacks?

**Q49:** What is Device Fingerprinting?

**Q50:** How does CAPTCHA help?

**Q51:** What role does WAF play?



