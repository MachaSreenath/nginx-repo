# 🚀 HTML Deployment using GitHub Actions (CI/CD)

This project uses **GitHub Actions** to automatically deploy an HTML file to **TEST and PROD servers** running **Nginx** whenever code is pushed to the `main` branch.

---

## 🔁 Workflow Trigger

- The workflow runs automatically on:
  - `git push` to the **main** branch

---

## 🧪 TEST Deployment Job

This job deploys the HTML file to the **TEST EC2 server**.

### Steps:
1. **Checkout Code**
   - Fetches the latest code from the repository.

2. **Deploy HTML to TEST Server**
   - Copies `index.html` to the Nginx directory:
     ```
     /usr/share/nginx/html/
     ```

3. **Restart Nginx**
   - Restarts the Nginx service on the TEST server to apply changes.

---

## 🚀 PROD Deployment Job

This job runs **only after the TEST deployment is successful**.

### Steps:
1. **Checkout Code**
   - Fetches the latest code again.

2. **Deploy HTML to PROD Server**
   - Copies `index.html` to the PROD server using SCP.

3. **Restart Nginx**
   - Restarts Nginx on the PROD server.

---

## 🔐 GitHub Secrets Used

The following secrets are configured in the GitHub repository:

| Secret Name     | Description                     |
|-----------------|---------------------------------|
| `EC2_HOST`      | TEST server public IP           |
| `PROD_SERVER`   | PROD server public IP           |
| `EC2_USER`      | SSH username (e.g., `ubuntu`)   |
| `SSH_KEY`       | Private SSH key for EC2 access |

---

## 🛠 Tools & Technologies

- GitHub Actions
- AWS EC2
- Nginx
- SSH & SCP

---

## ✅ Benefits

- Automatic deployment on code push
- Separate TEST and PROD environments
- Secure deployment using SSH keys
- No manual server access required
- Beginner-friendly CI/CD pipeline

---

## 📌 Summary

This project demonstrates a simple **CI/CD pipeline** where HTML files are automatically deployed to Nginx servers using GitHub Actions, making deployments fast, secure, and reliable.
