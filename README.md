# event-driven-streaming-platform

Hands-on exploration of modern distributed system design using **event-driven architecture** on Kubernetes.

The goal is to build a small but realistic platform that ties together **streaming** (Apache Kafka), **messaging** (RabbitMQ), **change data capture** (Debezium), and **observability**, with attention to scalability, resilience, data consistency, and operational concerns (lag, CDC health, queues).

## Roadmap and visibility

Detailed stories, tasks, and future evolutions are tracked in [`TODO.md`](TODO.md). Use it as the single place for backlog visibility and incremental delivery.

Engineering principles and Spec Kit governance for this repo are in [`.specify/memory/constitution.md`](.specify/memory/constitution.md).

## Prerequisites

Assumes familiarity with containers/Kubernetes basics and willingness to work with Kafka, relational databases, and message brokers as you go through the epics.
