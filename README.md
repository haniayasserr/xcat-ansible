# xcat-ansible

This repository automates the setup and configuration of an **xCAT (Extreme Cloud Administration Toolkit)** management node using **Ansible** and **Vagrant**.

It includes all Ansible role components required to install, configure, and manage the xCAT management node, as well as a predefined Vagrant environment for testing.

---

## 📦 Role: `xcat-management`

This is the primary Ansible role for setting up the xCAT management node.

### 1. **Defaults** (`defaults/main.yml`)
- Contains default variables for the role.
- Can be overridden by higher-precedence variables.
- Includes:
  - xCAT installation defaults
  - General configuration values

### 2. **Files** (`files/`)
- Stores static files that can be copied to managed nodes.
- Currently empty.
- Could be used for:
  - License files
  - Helper scripts
  - Pre-generated configs

### 3. **Handlers** (`handlers/main.yml`)
- Defines tasks triggered only when notified by other tasks.
- Used for:
  - Restarting xCAT services after configuration changes
  - Reloading dependent services

### 4. **Tasks** (`tasks/main.yml`)
- The main set of actions run by the role.
- Includes:
  - Package installation
  - xCAT configuration
  - Service management
  - xCAT user creation

### 5. **Templates** (`templates/`)
- Contains **Jinja2** template files rendered dynamically with Ansible variables.
- Includes:
  - `hosts.j2` → Generates `/etc/hosts`
  - `site.tab.j2` → Configures the xCAT site table

### 6. **Vars** (`vars/main.yml`)
- Stores role-specific variables (higher priority than defaults).
- Includes:
  - OS-specific package names
  - Path configurations
  - Network settings

---

## ⚙️ What This Role Does
The `xcat-management` role:

1. Installs xCAT management node packages.
2. Configures required system files (e.g., `/etc/hosts`).
3. Deploys xCAT configuration templates.
4. Manages and restarts xCAT-related services.
5. Handles OS-specific dependencies and package installation.

---

## Output 

[![Vagrant Init](https://raw.githubusercontent.com/haniayasserr/xcat-ansible/main/trying-again/Screenshot(215).png)](https://raw.githubusercontent.com/haniayasserr/xcat-ansible/main/trying-again/Screenshot%28215%29.png
)


## 📂 Project Structure




# tree
tree
.
├── Vagrantfile
├── ansible.cfg
├── group_vars
│   └── all.yml
├── inventory
│   └── hosts.yml
├── playbooks
│   ├── install_xcat.yml
│   ├── roles
│   │   └── xcat-management
│   │       ├── defaults
│   │       │   └── main.yml
│   │       ├── files
│   │       ├── handlers
│   │       │   └── main.yml
│   │       ├── tasks
│   │       │   └── main.yml
│   │       ├── templates
│   │       │   ├── hosts.j2
│   │       │   └── site.tab.j2
│   │       └── vars
│   │           └── main.yml
│   └── site.yml
└── ssh_config

