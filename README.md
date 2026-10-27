# 🔐 Cybersecurity Home Lab

A hands-on cybersecurity engineering project focused on web application security, network analysis, Linux administration, and defensive security.

## 🎯 Project Objectives

- Build a controlled cybersecurity testing environment.
- Practice authorized security assessments against intentionally vulnerable applications.
- Analyze network services and HTTP responses.
- Document findings and recommend remediation.
- Develop practical skills through repeatable experiments.

## 🏗️ Lab Environment

| Component | Purpose |
|---|---|
| Windows | Host computer |
| Kali Linux | Security testing environment |
| Docker | Runs the practice application |
| OWASP Juice Shop | Intentionally vulnerable web application |
| Nmap | Local service discovery |
| Git and GitHub | Version control and documentation |

## 🧪 Completed Work

### 1. Local Lab Deployment
- Created a dedicated `CyberHomeLab` project directory.
- Started OWASP Juice Shop using Docker.
- Bound the application to `127.0.0.1:3000` to restrict access to the local Kali environment.

### 2. Initial Service Discovery
- Checked the listening port using `ss`.
- Scanned TCP port 3000 on localhost using Nmap.
- Confirmed that the service was reachable and returned an HTTP response.

### 3. Version Control
- Initialized a Git repository.
- Created the initial project commit.
- Published the README to GitHub.

## 🔒 Safety and Scope

All security testing is intended for systems I own or have explicit permission to assess. The vulnerable training application is used for educational purposes.

## 🚧 Planned Work

- Document the lab architecture.
- Perform selected OWASP Juice Shop security exercises.
- Record findings, evidence, and remediation recommendations.
- Explore HTTP traffic analysis with Burp Suite.
- Develop a lightweight security monitoring exercise.
- Publish sanitized screenshots and technical reports.

## 📚 Learning Outcomes

This project is intended to develop practical experience in:

- Linux command-line operations
- Web application security
- Network service discovery
- Docker fundamentals
- Technical documentation
- Git and GitHub workflows

## 📌 Project Status

**Status:** In progress

Completed activities are documented above. Planned activities will be marked complete only after implementation and verification.

## 👩‍💻 Author

**Aisha Sani Mailafiya**

GitHub: [@AYSHATSM](https://github.com/AYSHATSM)
