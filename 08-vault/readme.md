# Encryp YAML dengan Ansible Vault

Pada kasus ini kita akan melakukan encrypsi pada file yaml yang kita miliki, ini implementasinya dapat dilakukan untuk melakukan encryp inventory yang berisikan informasi sensitif seperti ip, user dan credential server.

Selain itu kita akan menjalankan file yang sudah di encryp tersebut.

**Password Encrypt yang digunakan sekarang :** ansible


## Encrypt file YAML
```
ansible-vault encrypt inventory.yml
```
Setelah itu kamu akan dimintai password encrypt
```
New Vault password: 
Confirm New Vault password: 
Encryption successful
```
Hasilnya file yang kamu encrypt tadi kurang lebih akan menjadi seperti berikut
```
$ANSIBLE_VAULT;1.1;AES256
61366637646130313463653631363930396435663634643535393364373364313131633033386661
3330306664343735323766363763666232306263626139660a346535653665383932333138613461
33636631356266323431633866653039366137383839316333303539313833313465303438313331
3063663139333936640a356234663538383865343835333831653230323139316162656339636663
39323566613462383964346465326161623935376566376436653838333365323838356563393636
37373131393162633266323566623465326665346366353866313666306463383439373739623463
64643031633130323632343232313635313863646532636564303534323736336232363639373762
34346336633633316566323864326437613332313732363262613030656633386363313436643237
37326435623830653338376538643766333131383635613730383264303663363765613461626336
3965646261353763363931653264386661653133623965653563

```


## Edit file Encrypt
```
ansible-vault edit inventory.yml
```
Kamu akan dimintai password untuk membuka file encrypsi dan terminal akan membuka editor seperti nano atau vim


## Ganti Password Encrypt
```
ansible-vault rekey inventory.yml
```


## Decrypt file YML
```
ansible-vault decrypt inventory.yml
```


## Menjalankan Playbook Encrypt
Untuk menjalankan ansible playbook dengan file yang encryp dapat kita gunakan perintah berikut
```
ansible-playbook -i inventory.yml playbook.yml --ask-vault-pass
```
Apabila kita tidak menggunakan --ask-vault-pass maka hasilnya akan seperti dibawah ini.
```
PLAY [Play 1] **********************************************************************************************************
skipping: no hosts matched

PLAY RECAP *************************************************************************************************************
```

Kecuali kita melakukan testing pada local computer kita, maka playbook bisa dijalankan karena hanya membaca localhost saja.