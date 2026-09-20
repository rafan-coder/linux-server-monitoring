# Linux Server Monitoring Dashboard

A beginner-friendly Linux server monitoring project built using Ubuntu, Prometheus, Node Exporter, and Grafana.

## Project Overview

This project monitors Linux server performance and visualizes important infrastructure metrics through a Grafana dashboard.

The monitoring system collects system-level metrics using Node Exporter, stores them in Prometheus, and displays them using Grafana.

## Architecture

Ubuntu Linux
      ↓
Node Exporter
      ↓
Prometheus
      ↓
Grafana
      ↓
Monitoring Dashboard

## Technologies Used

- Ubuntu Linux
- Prometheus
- Node Exporter
- Grafana
- PromQL
- WSL
- Git & GitHub

## Monitored Metrics

The Grafana dashboard monitors:

- CPU Usage
- RAM Usage
- Disk Usage
- Network Receive Traffic
- Network Transmit Traffic
- Server Uptime

## Implementation

### 1. Node Exporter

Node Exporter collects hardware and operating system metrics from the Linux system.

### 2. Prometheus

Prometheus collects and stores metrics from Node Exporter at regular intervals.

### 3. Grafana

Grafana connects to Prometheus and provides interactive dashboards for monitoring system performance.

## PromQL Queries

Example CPU usage query:

    100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)

Example memory usage query:

    100 * (1 - (node_memory_MemAvailable_bytes / node_memory_MemTotal_bytes))

## What I Learned

- Linux server monitoring
- Prometheus configuration
- Node Exporter
- PromQL
- Grafana dashboards
- System performance monitoring
- Basic infrastructure troubleshooting
- Git and GitHub workflow

## Project Purpose

This project was created to gain practical hands-on experience with Linux infrastructure monitoring and cloud/IT operations.
