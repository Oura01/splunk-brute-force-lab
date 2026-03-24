# Splunk Brute Force Detection Lab

## Overview
Detected brute force login attempts using Splunk Enterprise on Windows 11.
Ingested Windows Security Event Logs, hunted EventCode 4625 with SPL,
and built an automated detection alert.

## Tools Used
- Splunk Enterprise (Free Trial)
- Windows 11 Security Event Logs
- SPL (Splunk Query Language)

## What I Did
- Configured Windows audit policy using auditpol
- Connected Splunk to Windows Security Event Logs
- Detected failed login attempts (EventCode 4625)
- Investigated using SPL queries
- Built automated brute force detection alert

## SPL Queries Used
index=main EventCode=4625 | table _time, Account_Name, Source_Network_Address, Failure_Reason
index=main EventCode=4625 | stats count by Account_Name | where count > 3

## Files
- `Incident_Report_Brute_Force_Detection.docx` — Full incident report
- `screenshots/` — Evidence from Splunk

## MITRE ATT&CK Mapping
- Technique: T1110 — Brute Force
- Tactic: Credential Access

## Skills Demonstrated
Splunk, SIEM, Threat Detection, SPL, Windows Event Logs, Incident Response
