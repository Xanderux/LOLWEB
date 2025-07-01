---
title: Google Calendar
tags:
  - Command and Control
  - Data Exfiltration
---

# Google Calendar

## Description

Google Calendar is a widely used cloud service for scheduling and managing events.  
Attackers can abuse Google Calendar to perform covert Command and Control (C2) communications or data exfiltration by encoding information in calendar events, event descriptions, or metadata.

---

## Technique

- Creating and modifying calendar events to exchange encoded commands or data.
- Using event descriptions or titles to hide payloads or instructions.
- Leveraging shared calendars or invitations to communicate between compromised systems.
- Automating calendar updates via Google Calendar API to maintain stealthy communication channels.

---

## Examples of Abuse

- Exfiltrating data by encoding it into event descriptions or titles.
- Sending commands through scheduled events that infected hosts poll regularly.
- Using shared calendars as a covert channel to bypass network monitoring.
- Coordinating multi-stage attacks through calendar event updates.

---

## Detection and Mitigation

### Indicators

- Monitor your infrastructure for high frequency of requests to `https://www.googleapis.com/calendar/v3`

---

## References

- [Google Calendar API Documentation](https://developers.google.com/calendar)
- [Google Threat Intelligence Group, Mark Your Calendar: APT41 Innovative Tactics](https://cloud.google.com/blog/topics/threat-intelligence/apt41-innovative-tactics)


---