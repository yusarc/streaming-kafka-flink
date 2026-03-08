# Stream Processing with Kafka and Pyflink

### This repository contains my implementation of the “Stream Processing with PyFlink” workshop by Alexey Grigorev.In this project I build a real‑time streaming pipeline step by step, starting from a message broker, producer, and consumer, and then adding a database and finally a stream processing framework.
​
By the end of the pipeline, the architecture is:

Producer (Python) → Kafka (Redpanda) → Flink (PyFlink) → PostgreSQL ​

The data source throughout the workshop is the NYC Yellow Taxi trip dataset.
​

### What I Built
The main goal of this repo is to implement a small but realistic streaming system:

A Kafka‑compatible broker using Redpanda

A Python producer sending NYC taxi rides as JSON messages

A Python consumer for debugging and inspection

A PostgreSQL database as a durable sink

A PyFlink job that reads from Kafka, applies event‑time windowed aggregations, and writes aggregated results back to PostgreSQL
​

This setup demonstrates how to go from raw events to stateful, windowed analytics using modern stream processing tools.

### Architecture

NYC Taxi Data (Parquet/Realtime)
        |
        v
Python Producer  -->  Redpanda (Kafka protocol)  -->  PyFlink Job  -->  PostgreSQL
                                     ^
                                     |
                             Python Consumer (debug)


### Producer

Reads NYC Yellow Taxi data (Parquet)

Converts rows into a typed Ride dataclass

Serializes to JSON and sends messages to a Kafka topic (rides)
​

### Broker (Redpanda)

Kafka‑compatible broker, single container, no JVM, no ZooKeeper
​

Exposes ports for internal (Docker) and external (host) clients
​

### Consumer (Python)

Subscribes to the rides topic

Deserializes JSON back into Ride objects

Prints messages to the console or writes to PostgreSQL
​

### Stream Processing (PyFlink)

Reads from the rides Kafka topic

Uses event‑time and watermarks, with tumbling windows

Aggregates metrics (e.g. trips and revenue per pickup location per hour)

Writes results as upserts into PostgreSQL tables
​

### Prerequisites
To run everything locally, you will need:

Docker and Docker Compose

Python 3.9+

uv (for Python environment and dependency management)

A SQL client (e.g. pgcli, DBeaver, pgAdmin, or DataGrip)
​





