# 2. Kafka version decision

Date: 2026-10-29

## Status

Proposed

## Context

This Kafka cluster serves the local development environment for the DDD demo and practice.
We try not to choose the latest version, to avoid major and minor bugs.
As of 2026-10-29, the latest release is 4.3.2 (released 2026-10-20), according to https://endoflife.date/apache-kafka.

## Decision

We will use Apache Kafka 4.3.1, the release just before the latest.

## Consequences

Positive:
- 4.3 is still a supported release line.

Negative:
- Bug fixes included in 4.3.2 are not applied.
