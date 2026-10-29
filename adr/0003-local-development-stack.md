# 3. Local development stack decision

Date: 2026-10-29

## Status

Proposed

## Context

Kafka and PostgreSQL are open only to the local environment for the DDD demo and practice.
Considering this is a local test environment, service ports should not conflict.

## Decision

We will use the following versions and ports.

| Item | Value |
|---|---|
| Kafka version | 4.3.2 |
| Kafka port for host clients | 9092 (default) |
| Kafka port for containers | 29092 |
| KRaft controller port | 9093 |
| PostgreSQL version | 18.6 |
| PostgreSQL port | 5432 (default) |

Demo services on the host can access Kafka at PLAINTEXT://127.0.0.1:9092 and PostgreSQL at postgresql://127.0.0.1:5432.

## Consequences

Positive:
- Host clients can use the default ports (Kafka 9092, PostgreSQL 5432) without extra configuration.

Negative:
- Kafka clients must use a different address depending on where they run (on the host or in a container).
- PostgreSQL conflicts with a PostgreSQL server already running locally on 5432.
