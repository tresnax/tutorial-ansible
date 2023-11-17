# Belajar Ansible 
| [EN](/readme-eng.md) | [ID](/readme.md) |


Panduan ini merupakan sebuah catatan sederhana untuk belajar Ansible beserta dengan beberapa studi case didalamnya. Dan mungkin akan mendapatkan update sesuai dengan case baru yang penulis dapatkan kedepannya.

## Daftar Isi
- [Apa itu ansbile ?](#apa-itu-ansbile-)
- [Komponen Utama](#komponen-utama)
    - [Inventory](#inventory)
    - [Playbook](#playbook)
- [Vagrant](#vagrant)
- [Roadmap Case](#roadmap-case)
- [Referensi](#reference)


## Apa itu ansible ?

Ansible sendiri merupakan sebuah tools automation yang akan membantu kamu untuk mempermudah proses post installation. Contohnya ketika kamu selesai melakukan installasi server kamu pasti akan melanjutkan installasi service seperi webserver, database server dll. Bayangkan apabila servernya banyak dan kamu harus melakukan manual pasti akan memakan waktu cukup banyak.

Dengan ansible kamu dapat membuat satu konfigurasi yang bisa digunakan secara berulang untuk server lainnya sehingga kamu hanya perlu menjalankan script tersebut.

## Komponen Utama

Ada 2 Komponen utama yang akan sering kamu temukan pada ansible, diantaranya :

### Inventory

Inventory merupakan file yang berikan informasi mengenai server/host yang akan menjadi target installasi, informasinya berisian alamat ip, username, password, port, dll. Contohnya :

```
all:
  hosts:                                    # Mendefinisikan bahwa ini host
    server1:                                # Nama dari host
      ansible_connection: ssh               # protocol yang digunakan
      ansible_host: "192.168.56.11"         # Alamat Host
      ansible_user: vagrant                 # Username Host
```

### Playbook

Playbook merupakan file yang berisikan script automasi yang akan kita jalankan nantinya, dalam playbook ini nanti akan di mention host mana yang akan menjalankan script tersebut dan apa saja task yang akan dijalankan pada saat file di eksekusi. Contohnya

```
- name: Playbook 1                          # Mendefinisikan Task playbook
  hosts: server1                            # Host yang akan dieksekusi sesuai inventory
  tasks:                                    # Memulai Task
    - name: membuat file test               # Nama task yang akan dijalankan
      command: touch /tmp/test.txt          # Eksekusi task (kasus ini adalah command)
```

### Menjalankan Ansible Playbook

Untuk menjalankan ansible anda hanya perlu menggunakan perintah berikut pada folder utama inventory dan playbook yang sudah dibuat.

```
ansible-playbook -i inventory.yml playbook.yml
```

## Vagrant

Pada panduan ini saya mengaplikasikan beberapa case menggunakan VM dengan bantuan vagrant, saya menyertakan juga Vagrantfile pada folder berikut [vagrant setup](/vagrant). Ini hanya optional saja, kamu bisa menggunakan server langsung atau cloud untuk mengaplikasikan vagrant ini.

Jika kamu berminat, kamu bisa pelajari vagrant pada link berikut [Belajar Vagrant](https://www.warriornux.com/mengenal-vagrant/)

## Roadmap Case

Berikut Roadmap yang dapat kamu ikuti untuk belajar mengenai Ansible :
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

Terima kasih banyak kepada kalian yang sudah menjadi referensi saya untuk menulis panduan sederhana ini :
- [Belajar Ansible Git - Naufal Afif](https://github.com/naufalafif/belajar-ansible)
- [Ansible Artikel - Lukman Lab](https://www.lukmanlab.com/tag/ansible/)
- [Chat Open AI](https://chat.openai.com/)