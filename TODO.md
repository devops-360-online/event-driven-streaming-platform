# TODO — event-driven-streaming-platform

Workshop backlog in checklist form. Main context: `[README.md](README.md)`.

**Suggested delivery order:** **4 → 1 → 2 → 3 → 5 → 6**.

View the raw source of this file to see checkbox nesting and optional metadata (`~estimate`, `#tag`).

### Todo

- [ ] **EPIC 4 — Kafka** — Publish order event (4.1) ~2d #epic4 #kafka
  - [ ] Define event format (`order_created`)
  - [ ] Produce message to Kafka; topic `orders`
  - [ ] Handle publish errors
- [ ] **EPIC 4 — Kafka** — Consume order events (4.2) ~2d #epic4
  - [ ] Create Kafka consumer
  - [ ] Manage offsets
  - [ ] Log received messages
- [ ] **EPIC 4 — Kafka** — Publish payment event (4.3) ~1d #epic4
  - [ ] Define event format (`payment_completed`)
  - [ ] Publish to topic `payments`
- [ ] **EPIC 1 — Orders** — Create order API (1.1) ~1d #epic1
  - [ ] `POST /orders` endpoint
  - [ ] Validate input
  - [ ] Persist order in DB
  - [ ] Return API response
- [ ] **EPIC 2 — Payment** — Process payment (2.1) ~2d #epic2
  - [ ] Consume `order_created`
  - [ ] Simulate payment
  - [ ] Handle errors; publish result (e.g. Kafka)
- [ ] **EPIC 2 — Payment** — Handle payment failures (2.2) ~2d #epic2
  - [ ] Retry logic
  - [ ] Log errors
  - [ ] Idempotency / deduplication
- [ ] **EPIC 3 — Notifications** — Send email notification (3.1) ~1d #epic3
  - [ ] Consume `payment_completed`
  - [ ] Resolve recipient email
  - [ ] Send email (mock or log)
- [ ] **EPIC 3 — Notifications** — Retry email sending (3.2) ~1d #epic3
  - [ ] Handle errors
  - [ ] Retry policy
- [ ] **EPIC 5 — Debezium** — Outbox pattern (5.1) ~2d #epic5 #cdc
  - [ ] Table `outbox_events`
  - [ ] Persist events in same transaction as business data
- [ ] **EPIC 5 — Debezium** — Debezium connector (5.2) ~2d #epic5
  - [ ] Configure connector with PostgreSQL
  - [ ] Publish to Kafka; validate CDC
  - [ ] *Future:* monitor via `__dbz_heartbeat`; watch disk on PostgreSQL
- [ ] **EPIC 6 — RabbitMQ** — Async email queue (6.1) ~2d #epic6
  - [ ] Queue `email_jobs`
  - [ ] Publish / consume messages
- [ ] **EPIC 6 — RabbitMQ** — Retry and DLQ (6.2) ~1d #epic6
  - [ ] Configure retries
  - [ ] Dead-letter queue (DLQ)
- [ ] **EPIC 7 — o11y** — Kafka observability (7.1) ~1d #epic7
  - [ ] Consumer lag (or equivalent)
- [ ] **EPIC 7 — o11y** — Debezium observability (7.2) ~1d #epic7
  - [ ] Heartbeats / connector health
  - [ ] Replication slot & partitioned tables (as applicable)
  - [ ] Disk when DBZ or PG is blocked
- [ ] **EPIC 7 — o11y** — RabbitMQ observability (7.3) ~1d #epic7
  - [ ] Queue depth / backlog

### In Progress

*(Nothing here yet — move a line from **Todo** when you start it.)*

### Done ✓

*(Completed stories go here with `[x]`, e.g. `- [x] **EPIC 4** — …`)*

---

### Reference — epics & stories (no checkboxes)


| Epic | Theme                                |
| ---- | ------------------------------------ |
| 1    | Order management                     |
| 4    | Event streaming (Kafka)              |
| 2    | Payment processing                   |
| 3    | Notification system                  |
| 5    | Data consistency (Debezium / outbox) |
| 6    | RabbitMQ                             |
| 7    | Observability                        |


