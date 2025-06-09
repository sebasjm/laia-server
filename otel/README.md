# laia-server


![image](https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white)

![image](https://img.shields.io/badge/Debian-A81D33?style=for-the-badge&logo=debian&logoColor=white)

![image](https://img.shields.io/badge/Grafana-F2F4F9?style=for-the-badge&logo=grafana&logoColor=orange&labelColor=F2F4F9)

---

# Installing OpenTelemetry Collector with Ansible

This project is designed to **install and configure the OpenTelemetry Collector** on **Debian-based operating systems** (such as Debian 12 or Ubuntu), using **Ansible**.

The generated configuration enables sending host-level metrics directly to **Grafana Cloud** using the OTLP protocol.

---

## 📦 Features

- Installs the official `.deb` package of the OpenTelemetry Collector.
- Sets up the service to start automatically.
- Uses a **Jinja2-based configuration template**.
- Integrates with **Grafana Cloud** using credentials securely stored with **Ansible Vault**.

---

## 🧰 Requirements

- Target OS: Debian 11, 12, or derivatives (e.g. Ubuntu)
- Python installed on the target host
- SSH access to the host with sudo privileges
- [Ansible](https://www.ansible.com/) installed on the control machine

---

## 🚀 Installing Ansible (on macOS)

Using Homebrew:

```bash
brew install ansible
```

---

## ▶️ Execution

Run the playbook with Vault support:

```bash
ansible-playbook site.yml --ask-vault-pass
```
