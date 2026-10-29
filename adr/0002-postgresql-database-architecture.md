# 2. PostgreSQL database architecture decision

Date: 2026-10-29

## Status

Proposed

## Context

This PostgreSQL database serves the local development environment for the DDD demo and practice.
It runs on a personal laptop for testing only.
Resilience and reliability of the database are not required.
Data for the demo and test environment must be stored in a persistent volume.

## Decision

We will run PostgreSQL as a single instance in a single container for convenience.
PostgreSQL data is stored in a Docker volume named "postgres-data".

## Consequences

Positive:
- The setup is simple: one container starts quickly and uses few laptop resources.
- Data persists across container restarts and recreation.

Negative:
- The single instance is a single point of failure. If it stops, the database is unavailable.
- Replication and failover cannot be tested.
