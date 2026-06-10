# Nmap Scan Detection

## Detection Name

Nmap Network Service Discovery Detection

## Data Source

Suricata IDS

## Objective

Detect network reconnaissance activity associated with Nmap scans against internal assets.

## SPL Query

```spl
index=suricata
signature="ET SCAN Nmap"
```

## Detection Logic

This detection identifies Suricata alerts generated when Nmap scanning activity is observed on the network. Nmap is commonly used during the reconnaissance phase of an attack to enumerate hosts, services, and exposed ports.

## MITRE ATT&CK Mapping

| Tactic    | Technique                 | ID    |
| --------- | ------------------------- | ----- |
| Discovery | Network Service Discovery | T1046 |

## Severity

Medium

## Validation

### Attack Source

Kali Linux

### Attack Command

```bash
nmap -A <target-ip>
```

### Expected Outcome

* Suricata generates an alert.
* Wazuh ingests the event.
* Splunk indexes the alert.
* Analyst can investigate the source and target systems.

## Investigation Steps

1. Identify the source IP.
2. Identify the destination host.
3. Review scan frequency and targeted ports.
4. Determine whether the activity was authorized.
5. Escalate if suspicious behavior persists.

## Evidence

* suricata-nmap-detection.png
* wazuh-nmap-detection.png
* splunk-wazuh-ingestion.png

## Recommendations

* Restrict unauthorized scanning activity.
* Monitor repeated reconnaissance attempts.
* Correlate with authentication and endpoint telemetry for additional context.
