# SOC Lab – Splunk Enterprise + Kali Linux

## 📌 Overview
This project demonstrates a hands-on Security Operations Center (SOC) lab using **Splunk Enterprise** and **Splunk Universal Forwarder** to collect and analyze Linux security events generated on a **Kali Linux host**.

The goal is to simulate real-world SOC activities such as log ingestion, authentication monitoring, and event analysis.

---

## 🧱 Lab Architecture
- **Splunk Server (Indexer & Search Head)**
  - IP: `192.168.10.104`
  - Listening on TCP `9997`
- **Kali Linux**
  - Splunk Universal Forwarder installed
  - System logs forwarded to Splunk


