# Incident Report

## Incident

Nmap Network Discovery

## Detection Source

Suricata IDS

## MITRE ATT&CK

T1046 - Network Service Discovery

## Executive Summary

An Nmap reconnaissance scan was launched from the Kali Linux attack host against a monitored asset within the lab environment. The activity was detected by Suricata IDS, ingested by Wazuh, indexed in Splunk, and reviewed during the investigation process.

## Description

The attack consisted of network service enumeration using Nmap. This activity represents the Discovery phase of the cyber attack lifecycle and is commonly performed by adversaries to identify accessible services and potential attack surfaces.

## Timeline

* 10:00 – Nmap scan initiated
* 10:01 – Suricata generated alert
* 10:01 – Wazuh ingested event
* 10:02 – Splunk indexed event
* 10:03 – Analyst investigation initiated
* 10:05 – Incident closed

## Impact

Low

The activity was generated within a controlled lab environment and did not result in compromise of any systems.

## Evidence

* suricata-nmap-detection.png
* wazuh-nmap-detection.png
* splunk-wazuh-ingestion.png
* kali-nmap-attack-simulation.png

## Detection Validation

The detection pipeline successfully tracked the attack across multiple telemetry layers:

Kali Linux → Suricata → Wazuh → Splunk → Analyst Investigation

## Recommendations

* Monitor repeated reconnaissance attempts.
* Correlate network scans with endpoint telemetry.
* Create automated enrichment workflows.
* Generate incident cases automatically for repeated scanning activity.
