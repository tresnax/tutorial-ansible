# Ansible Tutorial
| [EN](/readme-eng.md) | [ID](/readme.md) |


This guideline is a simple note to studying Ansible with some study case include. And maybe once time can have update for new case in future from author.


## Table of Content
- [What is Ansible ?](#what-is-ansbile-)
- [Main Component](#main-component)
    - [Inventory](#inventory)
    - [Playbook](#playbook)
- [Vagrant](#vagrant)
- [Roadmap Case](#roadmap-case)
- [Referensi](#reference)


## What is Ansible ?

Ansible is a tools automation that can help you easy to setup installation. Example when you after installing a server you must be installing service like web server, database, etc. Can you imagine if you must install manualy, maybe can take many time.

With ansible you can make one configuration that can used repeatly for any server so you can only running that script.


## Main Component

Ansible have 2 main component that can you often found, like :

### Inventory

Inventory is file that have information server/host can use to target installasion, the information in file like ip address, username, port, password, etc. Example :

```
all:
  hosts:                                    # Mendefinisikan bahwa ini host
    server1:                                # Nama dari host
      ansible_connection: ssh               # protocol yang digunakan
      ansible_host: "192.168.56.11"         # Alamat Host
      ansible_user: vagrant                 # Username Host
```

### Playbook

Playbook is file that have information for automation script then can we run, in playbook we can mention which host will run this script and what task can be execute. Example

```
- name: Playbook 1                          # Mendefinisikan Task playbook
  hosts: server1                            # Host yang akan dieksekusi sesuai inventory
  tasks:                                    # Memulai Task
    - name: membuat file test               # Nama task yang akan dijalankan
      command: touch /tmp/test.txt          # Eksekusi task (kasus ini adalah command)
```

### Running Ansible Playbook
For running Ansible we can use that command in main directory where we save the file inventory and playbook created.

```
ansible-playbook -i inventory.yml playbook.yml
```


## Vagrant
In this guideline i'm implement some case with VM using vagrant, i'm included Vagrant file too in directory [vagrant setup](/vagrant). It just optional, if you using on pemises or cloud server may you can't need this vagrant.

If you interest, you can learn how vagrant work in this link [Belajar Vagrant](https://www.warriornux.com/mengenal-vagrant/)


## Roadmap Case
This is roadmap that can you follow to learn about ansible :
1. [Menjalankan Ansible di Local](/01-run-ansbile-local)
2. [Ansible Conditional](/02-ansible-conditional)
3. [Ansible Loop](/03-ansible-loop)
4. [Ansible Variable](/04-ansible-variable)
5. [Notify & Handler](/05-notify-handler)
6. [Install Nginx di VM](/06-install-nginx)
7. [Deploy Docker di VM](/07-deploy-docker)
8. [Vault](/08-vault)
9. [Deploy with ssh password](/09-deploy-ssh-pass)
10. [Server Full Seup](/10-server-full-setup)
11. [Install kubernetes](/11-install-kubernetes)
12. [Fetch File](/12-fetch-file) 

## Reference

Thanks all of you to be my reference write this simple guideline :
- [Belajar Ansible Git - Naufal Afif](https://github.com/naufalafif/belajar-ansible)
- [Ansible Artikel - Lukman Lab](https://www.lukmanlab.com/tag/ansible/)
- [Chat Open AI](https://chat.openai.com/)