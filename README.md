# simrsgo2
opensource
1. Kebutuhan Hardware
  a. Server
      Minimal perangkat yang dibutuhkan yaitu
      Processor Xeon
      Memory 16GB
      HDD 512GB
  b. Client
      Minimal perangkat yang dibutuhkan yaitu
      Processor I3 / AMD
      Memory 2Gb
      HDD 256GB
 2. Kebutuhan Software
  a. Sistem Operasi
    1) Server
        Linux Centos 7 (direkomendasikan)
        Semua Jenis Linux
        Window Server 2008
    2) Client
        Windows 7
  b. Web Server
      Apache 2.4
      PHP 7
      MySQL 8
      Java 8
      Tomcat 9
      JavaBridge
      Library Jasper Report
      FTP Server
  c. Web Browser
      Chrome Versi 66 (direkomendasikan)
      Firefox Versi 59
  d. Tools lainnya
      Putty
      HeidiSQL
      Filezilla
 3. Instalasi
 2. Tekan tombol [ENTER] untuk mulai melakukan instalasi CentOS 7 with SIMRS GOS 2 tunggu beberapa saat sehingga muncul tampilan seperti pada gambar di bawah ini
 3. Ubah Date & Time sesuai lokasi masing – masing
 4. Pilih Installation Destination pilih disk sehingga tercentang kemudian pilih I will configure partitioning dan tekan tombol done
 5. Pilih CentOS Linux Linux 7.5.1804 for x86_64 Jika tidak ada lanjut ke point 9
 6. Pilih tombol minus [-]
 7. Centang delete all file systems
 8. Tekan tombol Delete It
 9. Kemudian click here to create them automatically
10. Jika ada /home maka dihapus 
11. Tambah ukuran space di centos root dengan home sebelumnya
    Contoh: centos-root: 50GB + home: 872.69GB = 922.69GB
12. Tekan tombol Done kemudian tekan tombol Accept Changes
13. Setelah itu tekan tombol Begin Installation
14. Tunggu sampai proses instalasi selesai kemudian tekan tombol Reboot
15. keluarkan/unmount cd/fdd instaler    
16. setelah boot selanjutnya setting Network 
    Sebelum melakukan konfigurasi jaringan, sistem akan meminta untuk memasukkan user/login dan password, default login dan passwordnya yaitu:
      Login: root
      Password: simrsgos
          Setelah masuk selanjutnya ketik perintah
            nmtui
            maka akan muncul menu 
            Pilih Edit a Conection (lakukan setting IP Static (recomended) atau DHCP)
     Restart jaringan mengetik perintah
        systemctl restart network
        Install tools
        Putty
        HeidiSQL
        Notepad++
    Konfigurasi MySQL (Membuat User, Import database SIMRS GOS 2)
      Sebelum melakukan konfigurasi MySQL terlebih dahulu melakukan mounting / memasukkan kembali cdrom (file iso)
      Perintah mounting:
        - Jika menggunakan CDROM
            mkdir /media/cdrom
            mount -t iso9660 /dev/sr0 /media/cdrom
        - Jika menggunakan Flash Disc
            mkdir /media/fd
            mount /dev/sdb1 /media/fd
        catatan: untuk melihat lokasi flash disc ketik perintah fdisk -l

17. Aktif ke direktori /media/cdrom atau /media/fd contoh:
    cd /media/fd
    cd postinstall/
    Eksekusi file mysql.conf.sh
    bash mysql.conf.sh
    tunggu sampai proses selesai
18. Mengizinkan port http, mysql, ftp & tomcat untuk dapat di akses dari computer klien
    Masih pada direktori yang sama ketik perintah
        bash allow.firewall.sh
    Jika selesai maka lakukan testing berikut
    - Akses aplikasi dengan alamat
        http://192.168.137.2/apps/SIMpel
            Nama pengguna: fatih
            Kata Sandi: simrsgos2
    - Akses tomcat
        http://192.168.137.2:8080
            username: simrsgos
            password: simrsgos
    - Remote akses database
            Username: admin
            Password: S!MRSGos2
    - Akses FTP
            Username: simrsgos
            Password: simrsgos
            
  setelah itu lakukan setting database di sesuaikan data dengan data kantor yang di inginkan
  
