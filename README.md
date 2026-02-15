# 🗼 OpsTower

OpsTower is a self-hosted DevOps and service management stack. It centralizes service management using **Komodo** and ensures a "security-first" deployment through automated secret generation and Ansible-based orchestration.

## 🚀 Overview

The goal of OpsTower is to provide a robust, automated infrastructure for home labs or edge computing. Instead of manual configuration, OpsTower uses **Ansible Playbooks** to:
- Provision containerized services.
- Provide a clear, secure deployment summary.

## 🛠 Tech Stack

- **Orchestration:** Ansible
- **Platform:** Docker & Docker Compose
- **Service Manager:** [Komodo](https://komo.do/)
- **Database:** MongoDB

## 🔐 Automated Secret Management

OpsTower prioritizes security by ensuring that no two deployments share the same credentials. On the first run, the playbook generates a `secrets.yaml` file containing:

- `setup_komodo_db_password`
- `setup_komodo_passkey`
- `setup_komodo_webhook_secret`
- `setup_komodo_jwt_secret`
- `setup_komodo_init_admin_password`

These secrets are generated using alphanumeric characters to prevent escaping issues and are stored with restricted permissions (`0600`).

## 📦 Installation & Deployment

### Prerequisites
- A server running a Debian-based OS. (!! ATTENTION: You will need a CPU with AVX support in order for mongodb to function !!)
- Ansible installed on your control machine.
- Docker and the `community.docker` Ansible collection.

### Quick Start

  1. **Clone the repository:**

      ```bash
      git clone https://github.com/KardBen/OpsTower.git
      cd OpsTower
      ````

  2. **Run the Playbook:**

      ```bash
      make setup
      make run
      ````

  3. **Access the Dashboard:**
    Once the playbook completes, a summary will appear in your console with your unique admin credentials. The WebUI is reachable by default at Port ``9120``.

## 🤝 Contributing
If you have suggestions for new services or improvements to the Ansible logic, feel free to open an issue or submit a pull request.

## 📄 License
Apache-2.0 license

## 👤 Author
Benjamin Kardumovic