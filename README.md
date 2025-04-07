# Ansible Playbook for Nginx Web Server Setup

## Overview
This playbook automates the deployment of a secure Nginx web server with:
- Two static web pages (`/page1` and `/page2`)
- Automatic SSL certificate generation via Certbot
- Firewall configuration with UFW
- System package updates

## File Structure
.ansible/
├── hosts
├── playbooks/
│ └── role_globallyhub.yml
└── roles/
└── Globallyhub-Task2/
  ├── tasks/
  │ └── main.yml
  ├── handlers/
  │ └── main.yml
  ├── templates/
  │ └── nginx_config.j2
  └── vars/
  └── main.yml



## Prerequisites
- Control machine with Ansible 2.9+
- Target server running Ubuntu 22.04
- SSH access with sudo privileges
- Domain name pointing to server IP

## Configuration

### 1. Inventory Setup (`~/.ansible/hosts`)
```ini
[servers]
5.189.163.205 ansible_user=anishchengre ansible_python_interpreter=/usr/bin/python3.12
```

### 2. Variables (vars/main.yml)
```
certbot_domain: globallyhub.tezhni.com
certbot_email: anishgharti.chhetry@gmail.com
ansible_user_id: anishchengre
```

### 3. Main Playbook (playbooks/role_globallyhub.yml)
```
---
- name: Install Nginx
  hosts: all
  roles:
    - Globallyhub-Task2
```
### Tasks (tasks/main.yml)
```
- name: Force Python 3.12 interpreter
  set_fact:
    ansible_python_interpreter: /usr/bin/python3.12

- name: Install system dependencies
  raw: |
    sudo apt-get update && 
    sudo apt-get install -y python3 python3-apt
  args:
    executable: /bin/bash

- name: Install Nginx
  command: sudo apt-get install -y nginx

- name: Create web directories
  file:
    path: "{{ item }}"
    state: directory
    owner: "{{ ansible_user_id }}"
    group: "{{ ansible_user_id }}"
    mode: '0755'
  loop:
    - /var/www/task1
    - /var/www/task2

- name: Deploy page content
  copy:
    content: |
      <h1>Page 1 Content</h1>
      <p>Custom HTML here</p>
    dest: /var/www/task1/index.html
    owner: "{{ ansible_user_id }}"
    group: "{{ ansible_user_id }}"
    mode: '0644'    
```


### Nginx Configuration (templates/nginx_config.j2)
```
server {
    listen 80;
    server_name {{ certbot_domain }};

    location /page1 {
        alias /var/www/task1/;
        index index.html;
    }

    location /page2 {
        alias /var/www/task2/;
        index index.html;
    }
}
```
### SSL Setup

- name: Run Certbot
  raw: |
    certbot --nginx --non-interactive --agree-tos --redirect -m {{ certbot_email }} -d {{ certbot_domain }}
  args:
    executable: /bin/bash
  retries: 3
  delay: 10


### Execution

ansible-playbook ~/.ansible/playbooks/role_globallyhub.yml


### Verification

Check Nginx status:

systemctl status nginx

Test web pages:

curl http://yourdomain.com/page1
curl https://yourdomain.com/page2

Verify SSL:

sudo certbot certificates