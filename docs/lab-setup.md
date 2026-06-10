# Lab Setup

## Overview

The Full Detection Pipeline Lab is a multi-layer Security Operations Center (SOC) environment designed to simulate real-world attack activity, collect security telemetry, correlate events across multiple platforms, and support incident investigation workflows.

## Components

| Component         | Purpose                                    |
| ----------------- | ------------------------------------------ |
| Kali Linux        | Attack simulation and adversary emulation  |
| Suricata IDS      | Network-based threat detection             |
| Wazuh Manager     | Security monitoring and event correlation  |
| Wazuh Agent       | Endpoint telemetry collection              |
| Splunk Enterprise | Log aggregation, search, and investigation |
| TheHive           | Incident and case management               |

## Detection Capabilities

The lab supports:

* Network Detection
* Endpoint Detection
* Log Correlation
* Threat Investigation
* MITRE ATT&CK Mapping
* Incident Management

## Security Workflow

Attack Simulation → Detection → Log Collection → Correlation → Investigation → Case Management

## Learning Objectives

This project demonstrates practical experience with:

* Detection Engineering
* Security Monitoring
* Incident Response
* SIEM Operations
* Threat Hunting Fundamentals
* SOC Analyst Workflows

## Current Use Case

The current implementation validates detection of Nmap reconnaissance activity generated from Kali Linux and tracked through Suricata, Wazuh, Splunk, and TheHive.

EOF
