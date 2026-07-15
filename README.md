---
title: Security Operations Center (SOC) Framework - Defensive Monitoring and Incident Response Assessment
date: 2026-07-14
author: Lindon Mitchell (YoguiCR)
role: Security Researcher / Junior SOC Analyst
status: Completed
classification: Public / Portfolio
environment: TryHackMe - SOC Fundamentals
---

---
## 1. Executive Summary
Technological advancement offers significant benefits to modern enterprises, primarily through the automation of workflows and increased operational efficiency. However, these advancements introduce substantial risks, as adversaries exploit the same technologies to compromise sensitive information, including proprietary databases, credentials, private information of employees/clients and financial assets.
Security breaches represent a critical threat to organizations of all sizes, potentially leading to catastrophic operational failures, legal repercussions, and severe financial insolvency. Regardless of an organization’s defensive posture, the possibility of an attack whether originating from external actors, internal threats, or the exploitation of physical assets remains constant.
This is where the Security Operations Center (SOC) serves as the frontline of the technology department. The SOC team is responsible for monitoring all organizational network traffic and managing user access, resources, and permissions to mitigate damage from suspicious activity. This continuous oversight makes the SOC indispensable for maintaining organizational integrity and resilience.

---

## **2. The SOC Workflow (El Manifiesto de Vuelo)**
A **Security Operations Center (SOC)** operates on a **24/7/365 execution model** to guarantee continuous visibility over organizational assets. Manually auditing every system, network segment, and endpoint is a resource-intensive process prone to human error. To optimize this workflow, the SOC utilizes specialized **Security Solutions** to centralize telemetry into a single "pane of glass," transforming raw data into actionable intelligence

**A. Strategic Security Solutions**
- **SIEM (Security Information and Event Management):** The central nervous system of the SOC. It collects logs from various network devices to be processed and analyzed. Modern SIEMs leverage **Artificial Intelligence (AI)** and **User Behavior Analytics (UBA)** to identify suspicious activity and reduce false negatives through advanced **Threat Intelligence** integration.
- **EDR (Endpoint Detection and Response):** Provides detailed real-time and historical visibility into all device activities across the network. The high-fidelity detection capabilities allow analysts to investigate anomalies at the endpoint level with precision.
- **Firewall:** The primary perimeter defense. It acts as a barrier between the internal and external network, filtering unauthorized traffic based on strict port and protocol rules (e.g., blocking **Port 445** to prevent credential leakage).

**B. Core Defensive Capabilities**
The SOC framework is designed to proactively detect and respond to:
- **Vulnerability Exploitation:** Identifying unpatched systems before they are compromised.
- **Unauthorized Activity:** Monitoring for anomalous behavior or lateral movement within the network.
- **Policy Violations:** Ensuring user's access, resources, and permissions align with the organization's security baselines.
- **Intrusion Detection:** Recognizing active threats and malicious actors attempting to breach the perimeter.

---

## 3. Incident Response & Escalation Procedures
Once a security incident is identified within the network telemetry, a standardized Incident Response protocol is triggered to minimize organizational impact and regain environmental control. This process begins with the generation of a **high-fidelity** alert, which is then escalated via a ticket system to a Senior SOC Analyst(Tier 2/3). Immediate tactical actions include restricting unauthorized access, preserving volatile forensic evidence, and initiating formal incident documentation.

**A. Critical Threat Neutralization**
High-severity threats that pose a critical risk to the organization such as active RCE attempts or credential leakage require immediate intervention from Tier 3 security engineers and leadership teams. The objective is to neutralize the adversary swiftly while performing a comprehensive impact assessment. This phase ensures that the organization understands the full scope of the breach before determining the strategic recovery steps required to maintain **Business Continuity**.

**B. Digital Forensics and Root Cause Analysis (RCA)**
In a complex scenario, the **Digital Forensics and Incident Response** **(DFIR)** team is deployed to conduct an exhaustive investigation. Their mission is to:

- **Identify the Root Cause:** Pinpointing the exact entry vector (e.g., an unpatched vulnerability or a spear-phishing link) to prevent re-infection
- **Lateral Movement Mapping:** Identifying all compromised systems and potential **data exfiltration paths**.
- **Eliminate Malicious Persistence:** Ensuring no backdoors, web shells, or dormant malware remain within the production environment, which could threaten future business operations

**C. False Positive Mitigation and Policy Tuning**
Not all alerts represent active threats; many are classified as **False Positives**. In these cases, no tactical response is required. However, the SOC team utilizes these events as feedback to fine-tune security detection policies, reducing "alert fatigue" optimizing and increases the SIEM’s accuracy, ensuring the team remains focused on high-priority telemetry.

**Note:** Incident response workflows and escalation matrices may vary significantly based on organizational size, industry regulations, and the specific nature of the alert. 

---

## 4. Business & HR Impact Analysis (Tu Ventaja Competitiva)
Drawing from my **8 years of experience** within the **Human Resources Department at the Municipalidad de Limón**, I have developed a deep understanding of the critical nature of organizational data. In a corporate environment, a **Security Operations Center (SOC)** acts as the vital guardian of human capital and institutional integrity.

The impact of a SOC on a business, particularly within an HR framework, includes:
- **Protection of Sensitive Data:** HR departments manage high-value targets for adversaries, such as **payroll databases, employee medical records,  Social Security data and confidential administrative files**. A proactive SOC monitors for unauthorized access to these records, preventing data exfiltration that could lead to identity theft or financial fraud.
- **Ensuring the CIA Triad:** When a SOC effectively monitors and protects directly upholds the **Confidencialidad, Integridad y Disponibilidad** of internal systems. It ensures that only authorized personnel can access or modify employee information, maintaining the accuracy of the organization's most sensitive records.
- **Mitigation of Legal and Financial Risks:** A security breach involving personal identifiable information (PII) can result in severe legal repercussions and financial insolvency for a company. The SOC’s ability to detect and neutralize threats early reduces the risk of massive litigation and operational downtime.
- **Organizational Trust:** By identifying policy violations or anomalous internal behavior, the SOC fosters a secure working environment, ensuring that the organization’s technology serves to empower employees rather than expose them to risk.

---

## **5. SIEM Dashboards parts**
![SEIM](+_)("SIEM Parts.png")

Here are the main components of this security alert screen from SIEM

##### **A. Top Navigation and Actions Bar**

- **Section Title:** Displays the name of the software "(SIEM Alerts)"
- **Search Bar:** A text input field ("Search Alerts") to filter specific events.
- **Global Action Buttons:** Two primary buttons to interact with the system, "Create alert" and "Create mass notification."
- **View Toggle:** A slider switch to "See all alerts."

##### **B. Left Side Panel (Saved Searches)**

A quick filter menu to organize security incidents by status:
- **All:** Every alert in the system.
- **Open / Closed:** Active or resolved cases.
- **Un'Acked:** Unacknowledged alerts that need review.
- **Not seen:** Unopened notifications.
- **Assigned to me:** Incidents directly linked to the active user account.
- **Encrypted Alerts:** Secured or protected notifications.

##### **C. Center Panel (Alerts List)**

Displays the feed of detected security incidents. Each individual alert block contains:

- **ID Number:** The unique tracking number for the event (e.g., `#167`, `#166`).
- **Priority Level (P):** Visual indicators of urgency, such as orange **P2** (High Priority) or yellow/grey **P3/P4** (Medium/Low Priority).
- **Incident Title:** Short description of the event (e.g., _"Port Scanning Activity Detected"_, _"Trojan Detected"_).
- **Context Tags:** Metadata showing the origin (**Network** or **Host**) and severity (**High-Severity**, **Medium-Severity**).
- **Assigned Group:** The collective responsible for handling the issue (the **SOC Team**).

##### **D. Management Details and Timestamps (Right Side)**

- **Assigned User:** The name of the specific security analyst handling the case (e.g., _Jaren Kade_, _Mira Talon_, _Dax Arden_).
- **Status Buttons:** Interactive labels indicating current state like **CLOSED** and **RESOLVED**, or action buttons like **ACKNOWLEDGE** and **OPEN**.
- **Date and Time:** The exact chronological log of when the threat was detected (e.g., _June 12, 2024 17:24_).

**Note:** This is a basic SIEM software, there are many different software in the market so this can change by brand and company

