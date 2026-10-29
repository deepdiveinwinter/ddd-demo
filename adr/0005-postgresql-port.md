# 5. PostgreSQL port decision

Date: 2026-10-29

## Status

Proposed

## Context

The PostgreSQL database is open only to the local environment.

## Decision

We will use PostgreSQL's default port 5432.
Demo services on the host can access PostgreSQL at postgresql://127.0.0.1:5432.

## Consequences

Positive:
- Host clients can use the default port without extra configuration.

Negative:
- It conflicts with a PostgreSQL server already running locally on 5432.
