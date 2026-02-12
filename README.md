
# Monitoring Lab – Prometheus & Grafana

This project demonstrates a basic infrastructure monitoring setup using **Prometheus** and **Grafana** across **Linux and Windows virtual machines**.

The goal of this lab is to simulate a small production-like environment and collect system metrics from multiple operating systems.

---

## Architecture Overview

       +----------------------+
       |   Windows 11 VM      |
       |  windows_exporter    |
       |  Port: 9182          |
       +----------+-----------+
                  |
                  | Metrics (HTTP)
                  v

---

## Technologies Used

- Prometheus (metrics collection)
- Grafana (visualization and dashboards)
- Windows Exporter (Windows system metrics)
- Node Exporter (Linux system metrics)
- VMware Workstation (virtualized lab environment)
- Ubuntu Linux
- Windows 11

---

## System Setup

### Linux VM (Monitoring Server)
Installed on Ubuntu:

- Prometheus
- Grafana
- Node Exporter

Responsibilities:
- Collect metrics from both Linux and Windows machines
- Store time-series data
- Provide dashboards through Grafana

---

### Windows VM (Monitored Host)

Installed:

- Windows Exporter (running as a service)
- Exposed metrics on:

Prometheus scrapes this endpoint to collect system data.

---

## Prometheus Targets

Configured targets:

- Linux Node Exporter: `localhost:9100`
- Windows Exporter: `<windows-ip>:9182`

Example configuration:

```yaml
scrape_configs:
  - job_name: 'linux'
    static_configs:
      - targets: ['localhost:9100']

  - job_name: 'windows'
    static_configs:
      - targets: ['<windows-ip>:9182']


