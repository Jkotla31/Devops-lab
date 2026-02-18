# Cloud Notes – AWS EC2 Practice

## ☁️ Instance Details
- Provider: AWS
- Service: EC2
- OS: Ubuntu Server
- Access Method: SSH using key pair

---

## 🔐 SSH Connection

Command used from WSL:

ssh -i ~/keys/devops-key.pem ubuntu@18.117.131.114

Why:
Used to securely connect to remote EC2 instance.

---

## 📦 Server Setup Steps

### Update packages
sudo apt update && sudo apt upgrade -y

Why:
Ensures latest security patches and stability.

---

### Install Git
sudo apt install git -y

Why:
Needed for pulling/pushing code repositories.

---

### Install nginx
sudo apt install nginx -y

Why:
Used as a web server / reverse proxy.

---

## 🌐 Service Verification

Check nginx status:

sudo systemctl status nginx

Check listening ports:

ss -tulnp

Why:
Confirms service is running and port 80 is open.

---

## 🔑 GitHub SSH Setup (EC2)

Generate key:

ssh-keygen -t ed25519 -C "your_email@example.com"

Add key to agent:

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

Why:
Allows secure GitHub authentication from EC2.

---

## 🚀 Git Workflow from EC2

Clone repo:

git clone git@github.com:Jkotla31/Devops-lab.git

Commit changes:

git add .
git commit -m "Update from EC2"
git push

Why:
Simulates real DevOps server-side code updates.

---

## 🎯 Key Learnings

- How to launch EC2 instance
- How SSH key authentication works
- Importance of chmod 400 for PEM files
- Installing and verifying services
- GitHub integration from server

---

## 🧠 Common Errors Faced

Permission denied (publickey)
Cause:
Wrong key / missing chmod / SSH misconfiguration

Fix:
chmod 400 devops-key.pems
ssh-add ~/.ssh/id_ed25519
Updated from AWS EC2 on Wed Feb 18 13:47:00 UTC 2026

