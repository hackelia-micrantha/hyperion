# 🌲 Hyperion

Hyperion (named after the world’s tallest tree) is an infrastructure-as-code project for creating environments and deploying services with minimal resources. It provides reusable automation and patterns for **local prototyping**, **staging validation**, and **production-ready deployments** on a VPS or cloud provider.  

---

## 🚀 Goals

1. **Minimal VPS Resources** — Lightweight by design, with [K3s](https://k3s.io) and Ansible-based provisioning.  
2. **Safe Production Deployments** — Blue/green and canary deployment strategies included.  
3. **Developer Velocity** — Simple prototyping flows for local development.  
4. **Multi-Environment Support** — Development, staging, testing, and production supported out of the box.  

---

## 📂 Repository Layout

### Public Repository
- 📖 **Documentation** — How to use and extend Hyperion.  
- 🔧 **Reusable Ansible Roles** — Common building blocks for provisioning.  
- ☸️ **Kubernetes Configurations** — Base manifests, kustomizations, and Helm charts.  
- 🔑 **CI/CD Pipelines** — GitHub Actions workflows, with secrets management.  

### Private Repository
- ⚙️ **Cluster Configurations** — Infrastructure definitions for full stacks.  
- 🐧 **K3s Deployment** — Automated with Ansible, provisioned with Terraform.  
- 🏗 **Services** grouped by scope:
  - `org/` → Organization services (`micrantha`)  
  - `personal/` → Personal projects (`ryjen`)  
  - `vendor/` → Third-party / vendor-managed services  
- 🌍 **Environments** — Configurations per environment:  
  - `production/`  
  - `staging/`  
  - `development/`  
  - `testing/` (via Vagrant + VirtualBox)  

---

## 🔄 Environments & Deployment

| Environment  | Purpose                                  | Deployment Target          |
|--------------|------------------------------------------|----------------------------|
| Development  | Fast local prototyping                   | Local K3s / Minikube       |
| Testing      | Integration testing w/ Vagrant & VirtualBox | Ephemeral VMs             |
| Staging      | Pre-production validation                | VPS / Cloud provider       |
| Production   | Blue/green & canary deployments          | VPS / Cloud provider       |

---

## 🛠 Toolchain

- **Terraform** → Provision cloud infrastructure (VPS, storage, networking).  
- **Ansible** → Automate K3s cluster setup and service deployment.  
- **Kubernetes (K3s)** → Lightweight cluster orchestration.  
- **FluxCD / GitOps** → Continuous deployment to clusters.  
- **Vagrant** → Local testing environment.  
- **GitHub Actions** → CI/CD pipelines with secrets.  

---

## 📜 Usage

Clone the public repo for documentation and shared roles/config:  
```bash
git clone https://github.com/<your-org>/hyperion.git
