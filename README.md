# Bulk Service Enable/Disable

## 🖊️ Scenario:
You need to manage multiple services on your systems. The task is to:
- **Enable services**: `sshd`, `crond`, `firewalld`.
- **Disable services**: `bluetooth`, `avahi-daemon`.

You need to ensure that the services `sshd`, `crond`, and `firewalld` are enabled and running, and the services `bluetooth` and `avahi-daemon` are disabled and stopped.

---

## ❓ Question:
How can you use an **Ansible Role** to manage these services automatically?

---

## ✅ Answer:
To automate this with Ansible, you can follow these steps:

### 1. **Create an Ansible Role** `servicemgmt`
This role will manage enabling and disabling the services based on the lists provided in a `vars` file.

### 2. **Define Service Lists**
In the `vars/main.yml` file, define two lists: one for **enabling services** and another for **disabling services**.

### 3. **Write Tasks for Managing Services**
In the `tasks/main.yml` file, use the `ansible.builtin.service` module to enable/disable services based on the defined lists.

### 4. **Create a Playbook**
Use a playbook to call the `servicemgmt` role and apply the changes.

---

## 🔹 Step-by-Step Implementation

### 1. **Create the Role Directory Structure**
First, create the role directory structure:

```bash
$ ansible-galaxy init servicemgmt
