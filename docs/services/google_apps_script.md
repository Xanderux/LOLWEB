---
title: Google Apps Script
tags:
  - Command and Control
  - Proxy Tunneling
---

# Google Apps Script

## Description

Google Apps Script is a cloud-based scripting platform that allows users to automate and extend Google Workspace applications (like Google Sheets, Docs, Gmail). It supports JavaScript code execution on Google servers, enabling powerful automation and integration.

Attackers abuse Google Apps Script to execute malicious code, establish Command and Control (C2) channels, and tunnel network traffic through legitimate Google infrastructure, effectively bypassing traditional network defenses.

---

## Technique

- Create and deploy malicious scripts within Google Workspace accounts.
- Use Apps Script's service to make HTTP requests to external C2 servers or proxy requests.
- Leverage triggers and timed executions for persistence and stealth.

---

## Examples of Abuse

- Setting up a C2 channel by fetching commands from a remote server and executing them.
- Proxying traffic through Apps Script to bypass firewall rules.
- Exfiltrating data from compromised accounts via Sheets, Gmail, or Drive.
- Automating phishing emails using Gmail APIs.

---

## Detection and Mitigation

### Indicators

- Google Apps Scripts use their own IP ranges, which are published by Google in [user-triggered-fetchers.json](https://developers.google.com/search/apis/ipranges/user-triggered-fetchers.json) and [user-triggered-fetchers-google.json](https://developers.google.com/search/apis/ipranges/user-triggered-fetchers-google.json). Monitor your infrastructure for an unusual number of requests originating from these IP ranges.

---

## References

- [Google Apps Script Official Documentation](https://developers.google.com/apps-script)

---