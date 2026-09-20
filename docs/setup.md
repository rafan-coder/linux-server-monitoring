# Setup Guide

## Environment

- Ubuntu Linux
- Prometheus
- Node Exporter
- Grafana

## Monitoring Flow

Ubuntu Server → Node Exporter → Prometheus → Grafana

## Prometheus

Prometheus runs on port 9090.

## Node Exporter

Node Exporter runs on port 9100.

## Grafana

Grafana runs on port 3000.

## Verification

Prometheus target:

http://localhost:9090

Node Exporter metrics:

http://localhost:9100/metrics

Grafana dashboard:

http://localhost:3000
