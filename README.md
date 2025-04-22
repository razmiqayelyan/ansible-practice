### ✅ Copy-Paste Ready `README.md`

```markdown
# Ansible Role-Based Apache Web Server Setup

This project uses Ansible's best practices to install and configure Apache web servers using a modular **role-based structure**. It supports both **Amazon Linux (RedHat-based)** and **Ubuntu (Debian-based)** systems.

## 📁 Project Structure

```
ansible/
├── site.yml                  # Main playbook
├── hosts                     # Inventory file
└── roles/
    └── webserver/
        ├── tasks/            # Task logic per OS
        ├── handlers/         # Apache restart handler
        ├── templates/        # Jinja2 HTML template
        └── files/            # Static website assets (CSS, JS, images)
```

## 🔧 Role Features

- Installs Apache (`httpd` or `apache2`) based on OS
- Deploys a dynamic `index.html` showing server IP using Jinja2 template
- Copies additional static assets
- Starts and enables Apache service
- Supports Ubuntu and Amazon Linux

## ⚙️ Requirements

- EC2 instances (Amazon Linux or Ubuntu)
- SSH access using `.pem` key
- Python + Ansible on the control node

## 🚀 Usage

Run the playbook using:

```bash
ansible-playbook site.yml
```

The playbook targets `all_servers` from your inventory and applies the `webserver` role.

## 🌐 Result

Each server will:
- Host a webpage at `/var/www/html/index.html`
- Show its own IP address on the page
- Serve additional content like styles and images
