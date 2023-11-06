# Belajar Ansible 

Panduan ini merupakan sebuah catatan sederhana untuk belajar Ansible beserta dengan beberapa studi case didalamnya. Dan mungkin akan mendapatkan update sesuai dengan case baru yang penulis dapatkan kedepannya.

## Apa sih ansible ?

Ansible sendiri merupakan sebuah tools automation yang akan membantu kamu untuk mempermudah proses post installation. Contohnya ketika kamu selesai melakukan installasi server kamu pasti akan melanjutkan installasi service seperi webserver, database server dll. Bayangkan apabila servernya banyak dan kamu harus melakukan manual pasti akan memakan waktu cukup banyak.

Dengan ansible kamu dapat membuat satu konfigurasi yang bisa digunakan secara berulang untuk server lainnya sehingga kamu hanya perlu menjalankan script tersebut.

## Istilah

Ada beberapa istilah yang akan sering kamu temukan pada ansible, diantaranya :
- Inventory
- Playbook
- Roles
- Vault
- Dll

### Inventory

Inventory merupakan file yang berikan informasi mengenai server/host yang akan menjadi target installasi, informasinya berisian alamat ip, username, password, port, dll.

### Playbook

Playbook merupakan file yang berisikan script automasi yang akan kita jalankan nantinya, dalam playbook ini nanti akan di mention host mana yang akan menjalankan script tersebut dan apa saja task yang akan dijalankan pada saat file di eksekusi.

### Roles

Roles merupakan fitur dari ansible untuk mengelompokan script menjadi beberapa bagian, sehingga hanya dengan 1 file playbook kita dapat menjalankan task sesuai dengan kebutuhan server sesuai dengan role. Misalkan didalam file kita membuat roles untuk webserver dan database server maka ketika kita melakukan eksekusi maka mereka hanya akan menjalankan proses tersebut saja.

### Vault

Vault merupakan fitur yang digunakan untuk meng-enkripsi file ansible sehingga tidak dapat dibaca secara langsung, ini menjadi salah satu fitur yang bisa digunakan untuk mengamankan file pada saat di distribusikan kepada tim yang akan menjalankan deployment tanpa takut credencialnya terbaca secara umum.

### Dll

Masih banyak fitur lainnya yang mungkin akan kita bahas secara detail kedepannya.

## Vagrant

Pada panduan ini saya mengaplikasikan beberapa case menggunakan VM dengan bantuan vagrant, saya menyertakan juga Vagrantfile pada folder berikut [vagrant setup](/tree/master/vagrant). Ini hanya optional saja, kamu bisa menggunakan server langsung atau cloud untuk mengaplikasikan vagrant ini.

Jika kamu berminat, kamu bisa pelajari vagrant pada link berikut [Belajar Vagrant](https://www.warriornux.com/mengenal-vagrant/)

## Roadmap Case

Berikut Roadmap yang dapat kamu ikuti untuk belajar mengenai Ansible :
1. Menjalankan Ansible di Local [Link](/tree/master/1-example)
2. Ansible Conditional [Link](/tree/master/2-example)
3. Ansible Loop [Link](/tree/master/3-example)
4. Ansible Variable [Link](/tree/master/4-example)
5. Notify & Handler [Link](/tree/master/5-example)
6. Install Nginx di VM [Link](/tree/master/6-example)
7. Deploy Docker di VM [Link](/tree/master/7-example)
8. Vault [Link](/tree/master/8-example)