# 🚀 Monitoring Stack with Terraform + Ansible + Docker

This project deploys a **Monitoring Stack** (Prometheus + Grafana) on **AWS EC2** using:  
- **Terraform** → Infrastructure provisioning  
- **Ansible** → Configuration management  
- **Docker + Docker Compose** → Containerized services  

---

## 📂 Project Structure



---

## ⚙️ Workflow
1. **Terraform** provisions EC2 instance + security groups (ports 22, 3000, 9090).  
2. **Ansible** installs Docker & Docker Compose, deploys monitoring stack.  
3. **Docker** runs Prometheus (metrics collection) and Grafana (visualization).  
4. **User** accesses dashboards in browser.  

---

## 🔧 Steps to Run

### 1. Provision Infrastructure with Terraform
```bash
cd terraform
terraform init
terraform apply -auto-approve


2. Configure Ansible Inventory
[monitoring]
<EC2_PUBLIC_IP> ansible_user=ec2-user ansible_ssh_private_key_file=~/.ssh/my-key.pem

3. Run Ansible Playbook
cd ansible
ansible-playbook -i inventory.ini playbook.yml

4. Access Dashboards
Prometheus → http://<EC2_PUBLIC_IP>:9090

Grafana → http://<EC2_PUBLIC_IP>:3000

Default login → admin / admin
