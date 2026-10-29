# 3. Kafka port decision

Date: 2026-10-29

## Status

Proposed

## Context

The Kafka cluster is open only to the local environment.
Considering this is a local test environment, service ports should not conflict.

## Decision

We will use 9092 for host clients, 29092 for containers, and 9093 for the KRaft controller.
Demo services on the host can access Kafka at PLAINTEXT://127.0.0.1:9092.

## Consequences

Positive:
- Host clients can use Kafka's default port 9092.

Negative:
- Clients must use a different address depending on where they run (on the host or in a container).
