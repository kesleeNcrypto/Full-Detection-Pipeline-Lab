# Detection Validation: Cross-Layer Analysis

## Objective

This phase validates detection coverage by analyzing how a single network-based attack is observed, correlated, and investigated across multiple telemetry layers.

The goal is to confirm that detection signals are:

*  Generated at the network layer
   
*  Correlated at the SIEM layer
  
*  Investigable within the analysis platform

## Test Scenario

A controlled network scan was executed from the attacker host:

```
nmap -sS 10.0.2.9
```


This simulates Network Service Discovery (MITRE T1046) — a common precursor to lateral movement and exploitation.

### Layer 1 — Network Detection (Suricata)

Suricata generated alerts based on signature matching and traffic inspection.

Observed:

+  Detection of TCP SYN scan behavior

+  Signature triggered (e.g., ET SCAN Nmap)

+  Source IP mapped to attacker host

+  Timestamp aligned with attack execution

This confirms early-stage detection at the network layer.

---

### Layer 2 — Correlation (Wazuh)

Wazuh ingested Suricata logs and generated structured alerts.

Observed:

+  Alert classification with rule level

+  Parsed JSON fields (source IP, event type)

+  Correlation based on incoming telemetry

This confirms successful normalization and correlation of network events.

---
### Layer 3 — Investigation (Splunk)

Wazuh alerts were ingested into Splunk via HTTP Event Collector.

Observed:

+  Searchable events within index=wazuh

+  Consistent source IP across events

+  Timeline reconstruction of scanning activity

Example query:
```
index=wazuh sourcetype="wazuh:alerts"
```

This confirms end-to-end visibility and investigation capability.
---
### Cross-Layer Correlation

The same attack was observed across all layers using:

*  Source IP correlation
*  Timestamp alignment
+  Event consistency

This validates:

A single attack produces multiple corroborating signals across telemetry layers.

### Detection Outcome
| Layer    | Result                   |
| -------- | ------------------------ |
| Suricata | Detected scan behavior   |
| Wazuh    | Correlated alert         |
| Splunk   | Investigation successful |

---
### Detection Engineering Insight
Detection reliability is not determined by a single alert, but by the ability to correlate signals across independent telemetry sources.

In this pipeline:

*  Suricata provided early detection

*  Wazuh provided structured correlation

*  Splunk provided investigation capability

This demonstrates a functional SOC detection workflow.

---

# Identified Gaps

*  No endpoint telemetry (Sysmon not yet integrated)

*  No automated correlation rules

*  No behavioral detection beyond signature-based alerts

---
# Next Step

Integration of endpoint telemetry (Sysmon) to:

1.  capture process-level activity

2.  validate behavior beyond network signals

3.  improve detection fidelity
