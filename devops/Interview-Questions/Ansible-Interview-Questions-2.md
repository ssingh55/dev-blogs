## What is configuration management ?

 > process of managing your software/system or hardware, lets in our premises we have lot of servers whether its on premise or cloud or anywhere and we want to manage 100 of servers to installation of couple of packages or you want to manage the upgradation of software or security patches, if we manually do or using some scripts then it will take lot of time to run on all the servers, and if we have different flavour of system we might end up writing multiple scripts
 and to manage it single handledly we can use either use configuration management tool like ansible, chef, puppet or any other configuraiton management tool

## Why ansible over the other configuration management tools
or
## Do u think ansible is better than other configuration management tool? if yes why ?

 > Ansible is agentless, if you want to configure 100 of servers, we dont have to install any agent on any of this servers,just like other tools where we require master slave architechture, only prerequisite we have to have passwordless authentication to all this servers from the hosts where ansible is installed
 > it uses very basic protocols if linux then its ssh and if its windows we use winrm
 > ansible is backed by a very good community bcoz ansible is written in python and its backed by redhat and other community members who used to build up there own purpose ansible
 > its using yaml for writing the ansible file

## Can you explain any Ansible Playbook that you wrote and found to be effective

 > 

## How ansible helped your organization 
 > (scenario based question to test your expertise in ansible)
 > just say one practical thing to interviewer and how it has helped you

## What is ansible dynamic inventory

 > It's a feature that allows Ansible to use external programs/scripts to dynamically generate inventory information.
 > This is particular used in environment where machines are frequently added or removed
 > Keep looking at what are the newly added machines and when there is a new added machines it deploy the changes

## Scenario: Lets assume you are not aware of the ansible servers that would be created in the future but still want to manage them. How can you achieve that

## What is ansible tower and have you used it? If yes, why?

 > 

## How do you manage the rbac of users for ansible tower?

## What is ansible galaxy command and why is it used?

## Can you explain me structure of ansible playbook using roles?

## What is handlers in ansible and why are they used

## I would like to run a specific set of tasks only on windows vms and not linux vms is it possible

## Does ansible support parallel execution of tasks

## what is  the protocol that ansible use to connect to windows vms

## Can you explain me the variable precedence in ansible

## How do u handle secrets in ansible

## Can ansible be used for IaC? Infrastructure as a Code?

## Write an ansible playbook to install and start httpd service on an existing ec2 instance
or
## Can you write an ansible playbook to install httpd service and get it running?

 > ask the interviewer what is the flavour of os

```
---
- name: Install and start apache http server
  hosts: 127.0.0.1
  become: yes
  tasks:
    - name: Update apt cache (for debian/ubuntu)
      apt:
        update_cache: yes
      when: ansible_os_family == "Debian"
    
    - name: Install Apache HTTP Server
      package:
        name: httpd # For Redhat/Centos
        state: present
      when: ansible_os_family == "RedHat"

    - name: Install Apache Http server
      package:
        name: apache2 # For debian/ubuntu
        state: present
      when: ansible_os_family == "Debian"

    - name: Check if http port is open in firewall (for Redhat/Centos)
      become: yes
      command: "firewall-cmd --query-service=http"
      register: firewall_http
      ignore_errors: true
      when: ansible_os_family == "RedHat"

    - name: Check if HTTP port is open in firewall (for Debian/ubuntu)
      become: yes
      command: "ufw status | grep -i http"
      register: firewall_http
      ignore_errors: true
      when: ansible_os_family == "Debian"
    
    - name: Open Http port in firewall (for redhat/centos)
      become: yes
      command: "firewall-cmd --permanent --add-service=http"
      when: firewall_http.rc != 0 and ansible_os_family == "Redhat"

    - name: Open http port in firewall (for Debian/Ubuntu)
      become: yes
      command: "ufw allow 'Apache Full'"
      when: firewall_http.rc != 0 and ansible_os_family == "Debian"


    - name:  Start  Apache service and enable it on boot
      service:
        name: httpd # For Redhat/Centos
        state: started
        enabled: yes
      when: ansible_os_family == "Redhat"

    - name: Start Apache service and enable it on boot
      service:
        name: apache2 # For Debian/Ubuntu
        state: started
        enabled: yes
      when: ansible_os_family == "Debian"
```

## Finally, what do you think that ansible can improve