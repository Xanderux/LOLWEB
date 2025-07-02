# Contributing to LOLWEB

Thank you for considering contributing to **LOLWEB**!  
This project aims to document legitimate web services that are abused for malicious purposes. It is powered by [MkDocs](https://www.mkdocs.org/) and hosted on GitHub Pages.

---

## 🧠 Project Scope

**LOLWEB** focuses on:
- Listing legitimate web services (e.g. platforms, APIs, file sharing, messaging).
- Providing documented use cases where these services are misused in cyberattacks.
- Structuring information to help threat analysts, CTI teams, and red/blue teams.

We **do not** cover:
- Generic IOCs or malware samples without context.
- Services that are inherently malicious or illegal.

---

## 🛠️ How to Contribute

### 1. Fork and Clone

```bash
git clone https://github.com/YOUR_USERNAME/LOLWEB.git
cd LOLWEB
```

### 2. Set Up the Environment

Make sure you have Python and pip installed.  
Then install MkDocs and dependencies:

```bash
pip install -r requirements.txt
```

### 3. Add or Update Content

All content is stored in the `docs/` folder.  
You can:

- Add a new Markdown file for a new service (e.g. `docs/services/telegram.md`)
- Update existing entries with new techniques, references, or mitigations.
- Keep the writing concise, factual, and well-referenced.

Each service page should ideally follow this structure:

```markdown
---
title: Service Name
tags:
  - Command and Control
  - Data Exfiltration
  - ...
---

# Service Name

## Description
Brief description of the service and its legitimate use.

---

## Technique
Describe how to implement the malicious use of this service.  
Include details such as protocols, APIs, payload delivery methods, redirection techniques, or other relevant technical steps.  
This section should help understand how an attacker sets up and uses the service during an operation.

---

## Examples of Abuse
Explain what types of malicious behaviors this service can support or conceal.  
Mention specific use cases like data exfiltration, C2 communication, phishing delivery, evasion techniques, etc.  
Include relevant TTPs and MITRE ATT&CK techniques when applicable.
---

## Detection and Mitigation

### Indicators
(Optional) Suggestions for detection or blocking without harming legitimate usage.

## References
Cite reports, articles, or public sources.
---
```

### 4. Build Locally

To preview your changes:

```bash
mkdocs serve
```

Open `http://127.0.0.1:8000/` in your browser.

### 5. Commit & Submit a Pull Request

```bash
git checkout -b your-feature-branch
git add .
git commit -m "Add service: ExampleService"
git push origin your-feature-branch
```

Then create a Pull Request to the `main` branch.

---

## 🧼 Style Guidelines

- Use clear, technical language.
- Reference sources whenever possible.
- Use Markdown syntax for formatting.
- Keep filenames and links lowercase and URL-friendly.

---

## 💬 Discussions & Issues

For ideas, questions, or doubts:
- Use [Discussions](https://github.com/Xanderux/LOLWEB/discussions)
- Or open an [Issue](https://github.com/Xanderux/LOLWEB/issues)

---

## 📜 License

By contributing, you agree that your contributions will be licensed under the same license as this project (MIT).

---

Thank you for helping improve LOLWEB! 💻
