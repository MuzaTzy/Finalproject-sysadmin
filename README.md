Nama : Muzakir M Nur
Nim : 22.83.0883

# Finalproject-sysadmin

1. Membuat web server menggunakan uamp
2. linux untuk sistem operasinya , apache sebagai software web server ,  mysql server sebagai database dan php sebagi pemrograman dinamisnya
3. menambahkan service ssh dan ftp
4. os yang di gunakan linux ubuntu 22.04 lts

# Install apache
- instal apache 2 
```bash
   apt install apache2
```

- periksa status apache
pastikan apache telah aktif
```bash
   apt install apache2
```

- Ubah pemilik folder “/var/www/html” dari root ke www-data
```bash
   sudo chown -R www-data:www-data /var/www/html
```

- Melakukan perizinan
Beri ijin anggota grup untuk merubah folder “/var/www/html”
```bash
   sudo chmod -R g+rw /var/www/html
```

- Membuat user
buat user anggota untuk bisa mengakses data
```bash
   sudo usermod -a -G www-data muza
```

- Membuat user
buat user anggota untuk bisa mengakses data
```bash
   sudo usermod -a -G www-data muza
```
- izinkan rule untuk apache di firewall
izinkan rule apache dan melihat status rule apache
```bash
   ufw allow apache
   ufw status
```

- pengetesan apache
apache telah di instal , lakukan pengecekan menggunakan web browser , ketikkan IP
![apache2](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/a4812eb5-17c1-4bd2-aa17-3f582a2b1c41)

# Install Mysql
- instal mysql-server 
```bash
   apt install mysql-server
```
- Jalankan skrip keamanan untuk meningkatkan keamanan database
```bash
   mysql_secure_installation
```
- Cek status MySQL
```bash
   service mysql status
```

# Install PHP
```bash
   apt install php libapache2-mod-php php-mysql
```

# Install phpmyadmin
```bash
   apt install phpmyadmin php-mbstring php-zip php-gd php-json php-curl
```
pilih apache2 menggunakan
![2](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/c65276f0-05e1-4155-837c-b3aa32edd64f)

konfigurasi database common , pilih yes
![3](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/7a4f980c-f726-4c39-a0c5-b52538b71303)

set password untuk mysql
![4](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/a8d3f9bc-8463-4a63-a61f-7f2dd10c2f81)

- mengonfigurasi akses kata sandi untuk akun root Mysql
```bash
   mysql
   mysql)ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY   'password';
   exit
```

- Restart apache
```bash
   Systemctl restart apache2
```

- Uji Coba phpmyadmin
http://192.168.13.3/phpmyadmin
![lasr](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/7073c518-ef34-4b4a-9112-d85060eb3d9f)

# Instalasi FTP

- instal ftp
```bash
   apt install vsftpd
```

- mengaktifkan port FTP
untuk perizinan komunikasi , ftp menggunakan port 21, setelah itu pastikan bahwa rule nya sudah berhasil
```bash
   ufw allow 21
   ufw status
```

- buat folder untuk user dan berikan izin
```bash
   mkdir /home/muza/ftp
   chown nobody:nogroup /home/ftpuser/ftp/
   chmod 777 /home/muza/ftp

```

- Cek status ftp
```bash
   systemctl status vsftpd
```

- Buat user ftp
```bash
   adduser muza
```
set password untuk menghubungkan ftp

- konfigurasi agar bisa mengupload file dari luar ke server 
```bash
   nano /etc/vsftpd.conf
```
lakukan konfigurasi, aktifkan write enable dengan cara meghapus tagar kemudian save

- restart ftp
```bash
   systemctl restart vsftpd
```

-buka file zila lalu koneksikan ftp dan coba upload file
![5](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/657d4b02-f3be-41fc-aea5-2455c8f3ec9d)

- restart apache 2 dan running di web browser
![hasil](https://github.com/MuzaTzy/Finalproject-sysadmin/assets/144196362/315dd8ad-4226-4ea0-81ba-b27c03da18cf)







