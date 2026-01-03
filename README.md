# 🚀 HTML Deployment with GitHub Actions (CI/CD)

This project automates the deployment of an **HTML file** to **TEST and PROD Nginx servers** using **GitHub Actions**.

---

## 🔁 Workflow

- **Trigger:** On push to `main` branch
- **TEST Deployment:** Copy `index.html` → restart Nginx
- **PROD Deployment:** Runs after TEST success, same steps for PROD server

---

## 🔐 GitHub Secrets

| Secret Name   | Purpose                     |
|---------------|----------------------------|
| `EC2_HOST`    | TEST server IP             |
| `PROD_SERVER` | PROD server IP             |
| `EC2_USER`    | SSH username (`ubuntu`)    |
| `SSH_KEY`     | Private SSH key for EC2    |

---

## 🛠 Tools & Technologies

- GitHub Actions | AWS EC2 | Nginx | SSH & SCP

---

## ✅ Key Benefits

- Fully automated deployments
- Separate TEST & PROD environments
- Secure via SSH keys
- No manual server access needed
- Beginner-friendly CI/CD showcase
