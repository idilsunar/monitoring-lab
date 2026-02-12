
# Architecture Overview

This document explains the architecture of the Monitoring Lab environment built using Prometheus and Grafana across Linux and Windows virtual machines.

## System Architecture

The lab simulates a small production-like monitoring setup with:

- One **Linux VM** acting as the monitoring server
- One **Windows VM** acting as the monitored host
- Prometheus collecting metrics
- Grafana visualizing system performance

+-------------------------+
|     Windows 11 VM       |
|-------------------------|
| windows_exporter        |
| Port: 9182              |
+-----------+-------------+
            |
            | HTTP Metrics
            v
+-------------------------+
|      Linux VM           |
|-------------------------|
| Prometheus (9090)       |
| Node Exporter (9100)    |
| Grafana (3000)          |
+-------------------------+

## Components
1. Linux Monitoring Server
Runs on an Ubuntu virtual machine.
## Installed services:
Prometheus – collects and stores metrics
Grafana – visualizes metrics through dashboards
Node Exporter – exposes Linux system metrics
 ## Main responsibilities:
Scrape metrics from both Linux and Windows machines
Store time-series monitoring data
Provide dashboards via Grafana
## 2. Windows Monitored Host
Runs on a Windows 11 virtual machine.
Installed service:
Windows Exporter (running as a Windows service)
## Function:
Exposing CPU usage, Memory usage, Disk I/O,Network traffic, Running services


