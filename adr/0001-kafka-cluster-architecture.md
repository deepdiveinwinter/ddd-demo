# 1. Kafka cluster architecture decision

Date: 2026-10-29

## Status

Proposed

## Context

This Kafka cluster serves the local development environment for the DDD demo and practice.
It runs on a personal laptop for testing only.
Resilience and reliability of the cluster are not required.
Data for the demo and test environment must be stored in a persistent volume.

## Decision

We will run the Kafka cluster in a single container for convenience.
The single Kafka node takes both the controller and broker roles (KRaft combined mode).
Kafka data is stored in a Docker volume named "kafka-data".

## Consequences

Positive:
- The setup is simple: one container starts quickly and uses few laptop resources.
- Topic data persists across container restarts and recreation.

Negative:
- The single node is a single point of failure. If it stops, the whole cluster is unavailable.
- Multi-broker behavior (replication, leader failover, ISR) cannot be tested, and internal topics must use a replication factor of 1.
