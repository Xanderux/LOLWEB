---
title: Cloudflare
tags:
  - IP masking via shared hosting/CDNs
---

# Cloudflare

## Description

Cloudflare is a widely used web service providing CDN, DDoS protection, and WAF capabilities to websites. It is available both as a free and paid service.

Attackers can abuse Cloudflare to **hide the real IP address** of a malicious server. By registering a domain and routing it through Cloudflare, the true backend infrastructure becomes difficult to identify for defenders unless misconfiguration or information leakage occurs.

---

## Technique

- The attacker hosts a malicious server on a VPS or compromised host with a real public IP.
- A malicious domain is registered (e.g., `malicious-site.com`).
- The attacker configures Cloudflare to act as a reverse proxy for the domain, pointing it to the backend server.
- Cloudflare handles TLS termination, WAF, and caching.
- The backend server is often configured (manually) to **only accept inbound traffic from Cloudflare IP ranges** (`https://www.cloudflare.com/ips/`), preventing direct probing or bypass.

This setup leverages **SNI-based virtual hosting** and **HTTP Host headers** to route traffic correctly behind shared Cloudflare IP addresses.

---

## Examples of Abuse

- **IP masking via CDN**: The true IP of the backend server remains obscured, making infrastructure takedown and attribution harder.
- **Rotating domains** while keeping the backend server unchanged and protected via CDN masking.

---

## Detection and Mitigation

### Indicators

- Monitor domain names with newly registered WHOIS pointing to Cloudflare IPs.

### Mitigation Strategies

- Focus on **domain-based blocking** and reputation rather than IP-based blocking, which may lead to collateral damage.
- Monitor for **newly registered domains** using Cloudflare, especially in phishing, malware, or fraud campaigns.
- Use passive TLS fingerprinting (JA3/JA4), DNS history, or traffic behavior to uncover misconfigured or leaking backends.
- Submit abuse reports to Cloudflare: [https://abuse.cloudflare.com](https://abuse.cloudflare.com)

---

## References

- [Cloudflare Abuse Report Form](https://abuse.cloudflare.com)
- [Understanding Reverse Proxies (Wikipedia)](https://en.wikipedia.org/wiki/Reverse_proxy)
- [Cloudflare Developer Documentation](https://developers.cloudflare.com/)
- [Cloudflare IP Ranges](https://www.cloudflare.com/ips/)
