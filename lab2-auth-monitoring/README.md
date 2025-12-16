# LAB 02 – SSH Authentication Monitoring with Splunk

## Overview
This lab demonstrates how to monitor Linux authentication events using Splunk.
SSH authentication failures generated on a Kali Linux host were forwarded,
indexed, and analyzed in Splunk.

## Architecture
- Kali Linux (log source)
- systemd-journald → rsyslog
- Splunk Universal Forwarder
- Splunk Enterprise (SIEM)

## Event Generation
SSH failed login attempts were intentionally generated using invalid credentials.

## Detection Queries

```spl
index=* source="/var/log/auth.log" "Failed password"
index=* source="/var/log/auth.log" "Failed password"
| stats count by host
| where count >= 3
