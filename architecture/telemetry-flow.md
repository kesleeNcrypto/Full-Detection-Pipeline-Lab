# Full Detection Pipeline — Telemetry Flow

## Overview

This project implements a cross-layer detection pipeline that correlates network telemetry, endpoint telemetry, and SIEM alerts to simulate a real SOC detection workflow.

The architecture integrates:

- Suricata for network detection
- Sysmon for endpoint telemetry
- Wazuh for detection and correlation
- Splunk for search and investigation
- TheHive for case management

## Detection Flow

### 1. Attack Simulation
Kali Linux is used to simulate attacker activity including discovery and credential access behavior.

### 2. Network Telemetry
Suricata captures suspicious traffic, connection attempts, and network-level indicators.

### 3. Endpoint Telemetry
Sysmon captures process execution, command activity, network connections, and file access on the target host.

### 4. Detection and Correlation
Wazuh aggregates and correlates telemetry from network and endpoint layers, producing normalized alerts.

### 5. Investigation
Splunk serves as the search and investigation layer for timeline review, event pivoting, and analysis.

### 6. Case Management
TheHive tracks the incident as a case and supports analyst workflow documentation.
