# Bulk Service Enable/Disable

## Scenario:
I need to manage multiple services on a systems. The task is to:
- **Enable services**: `sshd`, `crond`, `firewalld`.
- **Disable services**: `bluetooth`, `avahi-daemon`.

To ensure that the services `sshd`, `crond`, and `firewalld` are enabled and running, and the services `bluetooth` and `avahi-daemon` are disabled and stopped.

---

To automate this with Ansible, I have follow these steps:

### 1. **Create an Ansible Role** `servicemgmt`
$ ansible-galaxy init servicemgmt
This role will manage enabling and disabling the services based on the lists provided in a `vars` file.

### 2. **Define Service Lists**
In the `vars/main.yml` file, define two lists: one for **enabling services** and another for **disabling services**.

### 3. **Write Tasks for Managing Services**
In the `tasks/main.yml` file, enable/disable services based on the defined lists.

### 4. **Create a Playbook**
Use a playbook to call the `servicemgmt` role and apply the changes.
![image](https://github.com/user-attachments/assets/cddd3403-ec8a-420f-96fc-4e4a69e53e26)

---
