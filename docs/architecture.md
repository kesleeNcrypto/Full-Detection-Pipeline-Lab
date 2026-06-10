# Detection Architecture

## Overview

This project demonstrates an end-to-end Security Operations Center (SOC) detection pipeline capable of simulating attacks, collecting telemetry, correlating events, and supporting incident investigations.

## Components

### Kali Linux

Acts as the attack simulation platform used to generate reconnaissance and adversary activity.

### Suricata IDS

Monitors network traffic and generates alerts for suspicious activity such as Nmap scans and network reconnaissance.

### Wazuh

Collects endpoint and security telemetry, ingests Suricata alerts, and performs event correlation.

### Splunk

Centralizes log collection, indexing, searching, and investigation workflows.

### TheHive

Provides incident and case management capabilities for alert triage and response.

## Telemetry Flow

Kali Linux → Suricata → Wazuh → Splunk → TheHive

## Detection Pipeline

1. Attack activity originates from Kali Linux.
2. Suricata detects suspicious network behavior.
3. Wazuh collects and correlates telemetry.
4. Splunk indexes and visualizes events.
5. TheHive supports investigation and case management.

## Objective

Demonstrate cross-layer detection engineering across network telemetry, endpoint telemetry, SIEM correlation, and incident response workflows.

![Telemetry Diagram](../diagrams/telemetry.png)
