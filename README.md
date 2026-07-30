### Hi, I'm Ian 👋

I build production data infrastructure — streaming ingestion, layered warehouses, and the observability that keeps them honest. Lately I've been putting LLMs into production systems, which turns out to be mostly a systems engineering problem.

---

### Selected work

**[Real-time telemetry platform](https://github.com/jasonmar310/garmin-style-recovery-platform)**
Kafka → TimescaleDB + MinIO, with Prometheus/Grafana dashboards, four chaos-injected failure scenarios, and a runbook covering detection through prevention.

The question it was built to answer: *when consumer lag rises, is it load or backpressure?* Turns out throughput is the discriminator — lag up with throughput up means load; lag up with throughput flat means something downstream is stalling.

**0→1 KYC event pipeline** · *production*
Stripe webhooks are at-least-once by design. Converged to exactly-once using `event_id` as an idempotency key, with the dedup record and state transition committed in the same transaction — so "processed" and "applied" can't diverge. Replaced manual review for 500+ customers.

**Layered Snowflake warehouse** · *production*
RAW → STAGING → MART on dbt and Airflow. Watermark-based incremental extraction with partition-key upserts, so reruns and backfills never produce duplicates.

**LLM operations assistant** · *production*
A tool-calling agent on WhatsApp handling merchant onboarding and bookings. The hard part isn't the API — it's conversation state, idempotent side effects, and permission boundaries that keep an unreliable model from corrupting business data.

---

### How I think about this work

Guarantees belong in the system, not in the discipline of whoever uses it. Application checks can be bypassed; database constraints can't. Same idea one layer up — a good platform doesn't just stay up, it makes the people building on it fast.

---

### Stack

`Python` `TypeScript` `SQL` · `Kafka` `Airflow` `dbt` `Snowflake` `Iceberg` `TimescaleDB` · `Prometheus` `Grafana` · `PostgreSQL` `MySQL` `Redis` · `Docker` `AWS` `GitHub Actions` · `OpenAI` `LangChain` `RAG`

---

M.S. Applied Data Analytics, Boston University

📧 marso1998@gmail.com · [LinkedIn](https://www.linkedin.com/in/jialiang-ma)
