Nama : Muzakir M Nur
Nim : 22.83.0883

# Finalproject-sysadmin

1. Membuat web server menggunakan uamp
2. linux untuk sistem operasinya , apache sebagai software web server ,  mysql server sebagai database dan php sebagi pemrograman dinamisnya
3. menambahkan service ssh , dhcp, dan dns
4. os yang di gunakan linux ubuntu 22.04 lts

#Install phpmyadmin
```bash
   apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
```
pilih apache2 menggunakan
![2](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/c65276f0-05e1-4155-837c-b3aa32edd64f)

konfigurasi database common , pilih yes
![3](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/7a4f980c-f726-4c39-a0c5-b52538b71303)

set password untuk mysql
![4](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/a8d3f9bc-8463-4a63-a61f-7f2dd10c2f81)

#mengonfigurasi akses kata sandi untuk akun root Mysql
```bash
   mysql
   mysql)ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY   'password';
   exit
```
#Restart apache
```bash
   Systemctl restart apache2
```
#Uji Coba phpmyadmin
http://192.168.13.3/phpmyadmin
![lasr](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/7073c518-ef34-4b4a-9112-d85060eb3d9f)







