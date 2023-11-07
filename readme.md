# Belajar Ansible 

Panduan ini merupakan sebuah catatan sederhana untuk belajar Ansible beserta dengan beberapa studi case didalamnya. Dan mungkin akan mendapatkan update sesuai dengan case baru yang penulis dapatkan kedepannya.

## Daftar Isi
- [Apa itu ansbile ?](#apa-itu-ansbile-)
- [Komponen Utma](#komponen-utama)
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

Inventory merupakan file yang berikan informasi mengenai server/host yang akan menjadi target installasi, informasinya berisian alamat ip, username, password, port, dll.

### Playbook

Playbook merupakan file yang berisikan script automasi yang akan kita jalankan nantinya, dalam playbook ini nanti akan di mention host mana yang akan menjalankan script tersebut dan apa saja task yang akan dijalankan pada saat file di eksekusi.


## Vagrant

Pada panduan ini saya mengaplikasikan beberapa case menggunakan VM dengan bantuan vagrant, saya menyertakan juga Vagrantfile pada folder berikut [vagrant setup](/vagrant). Ini hanya optional saja, kamu bisa menggunakan server langsung atau cloud untuk mengaplikasikan vagrant ini.

Jika kamu berminat, kamu bisa pelajari vagrant pada link berikut [Belajar Vagrant](https://www.warriornux.com/mengenal-vagrant/)

## Roadmap Case

Berikut Roadmap yang dapat kamu ikuti untuk belajar mengenai Ansible :
1. [Menjalankan Ansible di Local](/1-run-ansbile-local)
2. [Ansible Conditional](/2-ansible-conditional)
3. [Ansible Loop](/3-ansible-loop)
4. [Ansible Variable](/4-ansible-variable)
5. [Notify & Handler](/5-notify-handler)
6. [Install Nginx di VM](/6-install-nginx)
7. [Deploy Docker di VM](/7-deploy-docker)
8. [Vault](/8-vault)
9. [Deploy with ssh password](/9-deploy-ssh-pass)

## Reference

Terima kasih banyak kepada kalian yang sudah menjadi referensi saya untuk menulis panduan sederhana ini :
- [Belajar Ansible Git - Naufal Afif](https://github.com/naufalafif/belajar-ansible)
- [Ansible Artikel - Lukman Lab](https://www.lukmanlab.com/cara-enkripsi-file-yaml-menggunakan-ansible-vault/)