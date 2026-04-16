---
title: Kafka
tags:
  - Resource
  - Topic/Messaging
status: stub
created: 2026-04-16
---

# Kafka

Apache Kafka is a distributed event streaming platform used for high-throughput, fault-tolerant publish-subscribe messaging.

## Key Ideas

- Producers write to topics; consumers read from topics via consumer groups
- Partitions enable parallelism and ordering guarantees within a partition
- Offsets track consumer position; committing offsets marks messages as processed
- Retention is time- or size-based, not acknowledgement-based — messages persist after consumption

## Related

- [[OpenTelemetry]]
