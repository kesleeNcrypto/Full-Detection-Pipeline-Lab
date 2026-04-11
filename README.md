# Full Detection Pipeline Lab

![Focus](https://img.shields.io/badge/Focus-Detection%20Engineering-orange)
![SIEM](https://img.shields.io/badge/SIEM-Splunk%20%7C%20Wazuh-blue)
![Telemetry](https://img.shields.io/badge/Telemetry-Suricata%20%7C%20Sysmon-lightgrey)
![Case%20Management](https://img.shields.io/badge/Case%20Management-TheHive-purple)
![Status](https://img.shields.io/badge/Project-Active-success)
![License](https://img.shields.io/badge/License-MIT-green)

## overview 
This project implements a **cross-layer detection engineering pipeline** designed to simulate how modern Security Operations Centers (SOC) detect, correlate, investigate, and respond to security events across multiple telemetry sources.

The lab integrates:

- **Suricata** — Network Detection  
- **Sysmon** — Endpoint Telemetry  
- **Wazuh** — Detection & Correlation  
- **Splunk** — Search & Investigation  
- **TheHive** — Case Management

  The objective is to validate how a **single attack chain** appears across multiple detection layers and how those signals are correlated into meaningful alerts and investigations.

---

## Why This Project Matters

Modern security environments rely on multiple telemetry sources.  
Single-layer detections often miss attack chains.

This project demonstrates:

- Cross-layer detection engineering  
- Telemetry correlation  
- SOC workflow simulation  
- Investigation-driven detection  
- Detection validation across multiple layers
- 
---

## Table of Contents

- [Overview](#overview)
- [Why This Project Matters](#why-this-project-matters)
- [Architecture](#architecture)
- [Project Objectives](#project-objectives)
- [Detection Pipeline Components](#detection-pipeline-components)
- [Phase 1 Attack Scenario](#phase-1-attack-scenario)
- [Expected Detection Flow](#expected-detection-flow)
- [Technologies Used](#technologies-used)
- [Repository Structure](#repository-structure)
- [MITRE ATT&CK Mapping](#mitre-attck-mapping)
- [Collaboration](#collaboration)
- [Project Status](#project-status)
- [Project Roadmap](#project-roadmap)
- [Future Enhancements](#future-enhancements)
- [Skills Demonstrated](#skills-demonstrated)
- [Author](#author)
- [License](#license)

---

## Architecture

This project uses a **cross-layer detection pipeline**:

![Full Detection Pipeline](architecture/architecture-diagram.png)

---

## Project Objectives

This lab focuses on:

- Cross-layer detection engineering  
- Telemetry correlation  
- SOC workflow simulation  
- Detection validation  
- Incident investigation  

---

## Detection Pipeline Components

### Network Detection — Suricata

Suricata monitors network traffic and detects:

- Suspicious connections  
- Port scanning  
- SSH attempts  
- Lateral movement behavior  
- Suspicious traffic patterns  

---

### Endpoint Telemetry — Sysmon

Sysmon collects endpoint telemetry including:

- Process creation  
- Network connections  
- Command execution  
- File creation  
- Authentication behavior  

---

### Detection & Correlation — Wazuh

Wazuh aggregates:

- Suricata alerts  
- Sysmon telemetry  
- System logs  

Wazuh performs:

- Detection correlation  
- Alert generation  
- Severity classification  
- MITRE ATT&CK mapping  

---

### Investigation Layer — Splunk

Splunk enables:

- Timeline investigation  
- Event correlation  
- Threat hunting  
- Alert analysis  
- Log searching  

---

### Case Management — TheHive

TheHive simulates SOC case handling:

- Incident creation  
- Alert tracking  
- Analyst workflow  
- Investigation documentation  

---

## Phase 1 Attack Scenario

Phase 1 focuses on:

**Discovery → Credential Access**

### Discovery Commands

```bash
whoami
hostname
netstat
ps aux
```

---

### Credential Access Simulation

- sudo attempts  
- failed login attempts  
- credential file access  

---

## Expected Detection Flow

| Layer | Detection |
|------|-----------|
| Suricata | Network activity |
| Sysmon | Endpoint behavior |
| Wazuh | Correlated alerts |
| Splunk | Investigation |
| TheHive | Case creation |

---

## Technologies Used

- Kali Linux  
- Suricata IDS  
- Sysmon  
- Wazuh  
- Splunk Enterprise  
- TheHive  
- VirtualBox  
- Linux  

---

## Repository Structure







## Repository Structure

```text
Full-Detection-Pipeline-Lab/
│
├── README.md
├── architecture/
│   ├── architecture-diagram.png
│   └── telemetry-flow.md
│
├── attack-simulation/
│   └── attack-flow.md
│
├── network-detection/
│   └── suricata-analysis.md
│
├── endpoint-detection/
│   └── sysmon-analysis.md
│
├── siem-correlation/
│   └── wazuh-correlation.md
│
├── investigation/
│   └── splunk-analysis.md
│
├── case-management/
│   └── thehive-workflow.md
│
├── mitre/
│   └── attack-mapping.md
│
├── artifacts/
│   └── screenshots/
│
└── docs/
    └── project-notes.md
```


---

## MITRE ATT&CK Mapping

This project maps detections to:

- T1087 — Account Discovery  
- T1033 — System Owner Discovery  
- T1049 — Network Connections Discovery  
- T1110 — Brute Force  
- T1078 — Valid Accounts  

---

## Collaboration

This project is being developed as a **collaborative detection engineering lab**.

### Roles

### Network & Detection Pipeline

- Suricata  
- Wazuh  
- Telemetry Flow  
- Architecture  

### Endpoint & Investigation

- Sysmon  
- TheHive  
- Investigation Workflow  

---

## Project Status

| Phase | Status |
|------|--------|
| Architecture | Complete |
| Repo Setup | Complete |
| Telemetry Design | Complete |
| Infrastructure Setup | In Progress |
| Attack Simulation | Pending |
| Correlation Testing | Pending |

---

## Project Roadmap

### Phase 1

- Cross-layer detection architecture  
- Discovery → Credential Access simulation  

### Phase 2

- Detection correlation validation  
- Investigation workflow  

### Phase 3

- MITRE ATT&CK mapping  
- Documentation  

### Phase 4

- Automation (n8n + AI)  
- SOC triage pipeline  

---

## Future Enhancements

- Splunk automation  
- n8n automation workflows  
- AI-powered alert triage  
- Cloud telemetry (AWS / Azure)  
- Threat hunting dashboards  

---

## Skills Demonstrated

- Detection Engineering  
- SIEM Architecture  
- Telemetry Correlation  
- SOC Workflow Design  
- Threat Detection  
- Incident Response  
- Blue Team Engineering  

---

## Author

**Esla Kwanza**  
Cybersecurity | Detection Engineering | SOC | Cloud Security  

GitHub:  
https://github.com/kesleeNcrypto

---

## License

MIT License




