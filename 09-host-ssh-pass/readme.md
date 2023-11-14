# Host with password SSH

## Service Tambahan
Untuk bisa menggunakan password pada informasi host, anda perlu mengintsallkan sshpass :
Ubuntu
```
sudo apt-get install sshpass
```
Fedora
```
sudo yum install sshpass
```
Arch
```
sudo pacman -Sy sshpass
```
## Vagrant

Untuk anda yang menggunakan vagrant untuk percobaan ini, anda bisa sesuaikan konfigruasi Vagrantfile seperti berikut.
```
Vagrant.configure("2") do |config|
  # Bagian ini digunakan apabila ingin connect ssh vagrant menggunakan user dan pass
  config.ssh.username = "ubuntu"
  config.ssh.password = "vagrant"
```
Lalu berikan tanda comment (#) pada bagian berikut
```
 #config.vm.provision "file", source: "~/.ssh/id_ed25519.pub", destination: "~/.ssh/me.pub"
  #config.vm.provision "shell", inline: <<-SHELL
  #cat /home/vagrant/.ssh/me.pub >> /home/vagrant/.ssh/authorized_keys
#SHELL
```