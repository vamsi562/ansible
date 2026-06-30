
## ping command

ansible all -i <ip_addr>, -e ansible_user=ec2-user -e ansible_password=DevOps321 -m ping

## Install nginx

ansible all -i <ip_addr>, -e ansible_user=ec2-user -e ansible_password=DevOps321 -b -m dnf -a "name=nginx state=installed"

10.0.8.125 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": true,
    "msg": "",
    "rc": 0,
    "results": [
        "Installed: redhat-logos-httpd-90.6-1.el9.noarch",
        "Installed: nginx-2:1.20.1-28.el9_8.3.x86_64",
        "Installed: nginx-core-2:1.20.1-28.el9_8.3.x86_64",
        "Installed: nginx-filesystem-2:1.20.1-28.el9_8.3.noarch"
    ]
}


ansible all -i <ip_addr>, -e ansible_user=ec2-user -e ansible_password=DevOps321 -b -m dnf -a "name=nginx state=installed"

'''
10.0.8.125 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "msg": "Nothing to do",
    "rc": 0,
    "results": []
}
''''


ansible all -i <ip_addr>, -e ansible_user=ec2-user -e ansible_password=DevOps321 -b -m service -a "name=nginx state=started"

### ansible playbook commands

ansible-playbook -i inventory.ini -e ansible_user=ec2-user -e ansible_password=DevOps321 01-playbook.yaml