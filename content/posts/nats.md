---
id: 1738767278-nats
aliases:
  - 1738767278-nats
  - Nats
tags:
  - nats
  - broker
  - pub_sub
  - pull_push
date: "2025-02-05"
title: Nats
---

# Nats

`Nats Core`

You need to adapt this solution for your own needs, as this is only the core.

`Nats - Jetstream`

In fact, it is used by most people; to run it, 2+ replicas are required.

`Stream`

- A stream is created

  - You create topics

  - You choose the type of data storage

    - In memory
    - On disk

  - You specify the retention policies
    - Based on message time
    - Based on the total number of messages
    - Based on the total number of bytes

`Consumers`

- A consumer is created

  - You choose the interaction pattern

    - Pub / Sub

      - There is a separation between the sender and the receiver.
        The sender may not know who the receiver is.
        Moreover, after sending and receiving an ACK, the sender does not wait for anything.
        - Pros
          - Independence
          - Scalability
          - Flexibility

    - Request / Reply
      - The client sends a request that includes a "reply to client" flag and waits for a response from the service.
        - Pros
          - Synchronous operations
          - Direct response handling
          - Simplicity
          - Speed

    - Queuing
      - Essentially, this is load balancing, with the backend being a queue that a group of receivers joins.
        - Pros
          - High fault tolerance
          - Optimal resource utilization
          - Even load distribution across each service

  - You choose the delivery pattern
    - Push-Based Consumer
      - Nats pushes messages as soon as they become available for sending
        - Pub/Sub
        - Request / Reply
        - Queuing
    - Pull-Based Consumer
      - The consumer requests messages when needed
        - Pub/Sub
        - Queuing

