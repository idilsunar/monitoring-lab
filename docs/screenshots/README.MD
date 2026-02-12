# Monitoring Dashboard Screenshots

This folder contains screenshots from the Grafana dashboards used in the Monitoring Lab.

The dashboards visualize system metrics collected by **Prometheus** from both the Linux and Windows virtual machines.

---

## Included Screenshots

### CPU and Network Overview
- Displays CPU load and usage metrics
- Shows network upload and download activity
- Collected from the Windows VM via Windows Exporter

### Network Traffic
- Visualizes bandwidth usage
- Shows upload and download rates over time
- Useful for detecting unusual traffic patterns

### Disk I/O
- Displays disk read and write activity
- Helps identify storage bottlenecks or abnormal disk usage

### Disk Space
- Shows available disk space using a gauge visualization
- Useful for capacity planning and alerting

### Services Overview
- Displays running and stopped Windows services
- Helps monitor system state and service health

---

## Notes

- These screenshots were captured from a lab environment running on virtual machines.
- IP addresses shown in the dashboards are from a private local network.
- The dashboards are powered by:
  - Prometheus (metrics collection)
  - Grafana (visualization)
  - Node Exporter (Linux metrics)
  - Windows Exporter (Windows metrics)
