# Ansible Role : Mesos

Ansible Role for Canaima Project's Apache Mesos.

# Requirements

- VirtualBox 6.x or above
- CentOS 7 with minimal install and latest patches


# Example Playbook

## Master node 

```
- name: Deploy Mesos master node for Canaima
  hosts: "{{ hosts }}"
  remote_user: "{{ user }}"
  tasks:
  - import_role:
      name: mesos
      tasks_from: install_master
    vars:
      install_mode: master
      vm_ip: "{{ mesos_master_ip }}"
      vm_name: mesos_master
      vm_memory: "{{ mesos_master_ram }}"
```

## Slave node
```
- name: Deploy Mesos for Canaima
  hosts: "{{ hosts }}"
  remote_user: "{{ user }}"
  tasks:
  - import_role:
      name: mesos
      tasks_from: install_slave
    vars:
      install_mode: slave
      vm_ip: "{{ mesos_slave_ip }}"
      vm_name: mesos_slave
      vm_memory: "{{ mesos_slave_ram }}"
```

# Author Information

* **Toréa TESSIER** - <torea.tessier2@gmail.com> - [Canaima Project](https://github.com/canaima-project)
