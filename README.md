# Stream Processing with Kafka and Pyflink

### This repository contains my implementation of the “Stream Processing with PyFlink” workshop by Alexey Grigorev (DataTalks.Club). It focuses on building end‑to‑end streaming pipelines in Python using PyFlink.

## Objectives
Learn the core concepts of stream processing with PyFlink

Work with event-time, watermarks, and windowing

Read data from streaming sources (e.g. NYC taxi rides)

Apply transformations and aggregations

Write results to different sinks (console, files, or other systems)

## Project Overview
The project simulates a simple streaming analytics pipeline:

Source: taxi ride events (e.g. NYC Yellow Taxi data)

Processing (PyFlink job): cleaning, transforming and aggregating events using event-time semantics

Sink: console output and/or files to inspect results

You can use this as a template or starting point for more advanced streaming experiments.

## Prerequisites
Python 3.9+

Git

(Optional but recommended) Docker and Docker Compose for local Flink/Kafka environments

A Unix-like shell (macOS/Linux) or WSL/PowerShell on Windows
