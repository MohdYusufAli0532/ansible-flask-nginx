# 🐧 Ansible + Flask + Nginx Automation

This project demonstrates how to use **Ansible** to provision and run a **Flask web application** behind **Nginx**.  
It is designed to run inside a container (using `cytopia/ansible`) and works without manual setup.

---

## 📂 Project Structure

```
ansible-flask-nginx/
├── app.py          # Sample Flask app
├── hosts.ini       # Ansible inventory
├── site.yml        # Main playbook
├── roles/
│   ├── common/     # Common dependencies (Python3, pip, Flask)
│   ├── flask/      # Flask setup + run
│   └── nginx/      # Nginx install + run
└── README.md
```

---

## ⚙️ Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed  
- Git installed  
- A GitHub repo (if you want to push this project)

---

## 🚀 Running the Project

### 1️⃣ Clone the repo
```bash
git clone https://github.com/mohdyusufali0532/ansible-flask-nginx.git
cd ansible-flask-nginx
```

### 2️⃣ Run the Ansible playbook inside Docker
```bash
docker run --rm -it   -p 80:80 -p 5000:5000   -v ${PWD}:/ansible/playbooks   -w /ansible/playbooks   cytopia/ansible ansible-playbook -i hosts.ini site.yml
```

---

## 🌐 Access the App

- Flask app runs on 👉 **http://localhost:5000**  
- Nginx serves on 👉 **http://localhost:80**

---

## 📌 Notes

- The playbook installs **Python3, pip, Flask, and Nginx** using Alpine’s apk.  
- Flask app is copied into `/opt/flask_app/`.  
- Nginx is started with a minimal config to serve Flask.  
- Modify **app.py** to change your Flask app’s logic.  

---

## 📝 License

This project is open-source under the **MIT License**.
