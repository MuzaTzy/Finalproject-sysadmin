Nama : Muzakir M Nur
Nim : 22.83.0883

# Finalproject-sysadmin

1. Membuat web server menggunakan uamp
2. linux untuk sistem operasinya , apache sebagai software web server ,  mysql server sebagai database dan php sebagi pemrograman dinamisnya
3. menambahkan service ssh , dhcp, dan dns
4. os yang di gunakan linux ubuntu 22.04 lts

#==Install phpmyadmin==
```bash
   apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
```
jika gagal saat proses install maka disabled komponen

Masu ke dalam mysql
#mysql
 mysql)UNINSTALL COMPONENT "file://component_validate_password";
 mysql)exit

Melanjutkan proses installasi phpmyadmin
#apt install phpmyadmin

Jika sudah berhasil proses install jangan lupa enabled komponen
#mysql
 mysql)INSTALL COMPONENT "file://component_validate_password";
 mysql)exit
#phpenmod mbstring
#systemctl restart apache2

Mengonfigurasi Akses Kata Sandi untuk Akun Root MySQL
#mysql
 mysql)ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'password';
atau jika gagal bisa menggunakan cara lain sbb
 mysql)ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
 mysql)exit

Uji Coba phpmyadmin
http://your_domain_or_IP/phpmyadmin


