# 50 Perintah Lanjutan Ubuntu / Linux

Berikut adalah daftar 50 perintah terminal Ubuntu/Linux yang berbeda, berfokus pada level menengah hingga lanjut (termasuk manajemen kernel, diagnostik jaringan tingkat lanjut, pemrosesan teks tingkat lanjut seperti `awk` dan `sed`, serta administrasi sistem),.

---

### 1. `route`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Menampilkan atau memanipulasi tabel routing IP kernel.
* **Sintaks:** `route -n`
* **Contoh Penggunaan:**
```bash
route -n
```

### 2. `tcpdump`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Menganalisis paket jaringan (packet sniffer) secara langsung lewat terminal.
* **Sintaks:** `sudo tcpdump -i [interface]`
* **Contoh Penggunaan:**
```bash
sudo tcpdump -i eth0 port 80
# Menangkap lalu lintas data pada port HTTP (80)
```

### 3. `basename`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Menghilangkan direktori dan ekstensi dari jalur file, hanya menyisakan nama file.
* **Sintaks:** `basename [jalur_file]`
* **Contoh Penggunaan:**
```bash
basename /var/www/html/index.php
# Output: index.php
```

### 4. `sed`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Stream editor untuk melakukan pencarian, penyisipan, dan penggantian teks secara otomatis.
* **Sintaks:** `sed 's/[teks_lama]/[teks_baru]/g' [file]`
* **Contoh Penggunaan:**
```bash
sed 's/anjing/kucing/g' cerita.txt
# Mengganti semua kata 'anjing' dengan 'kucing'
```

### 5. `lsof`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Menampilkan daftar file yang sedang dibuka oleh proses apa pun di sistem.
* **Sintaks:** `lsof -i [port/protokol]`
* **Contoh Penggunaan:**
```bash
lsof -i :80
# Mengecek proses apa yang menggunakan port 80
```

### 6. `tee`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Membaca dari standar input dan menulis ke file sekaligus standar output.
* **Sintaks:** `perintah | tee [nama_file]`
* **Contoh Penggunaan:**
```bash
uname -a | tee info_sistem.txt
```

### 7. `scp`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Menyalin file secara aman antar komputer melalui jaringan menggunakan SSH.
* **Sintaks:** `scp [file_lokal] [user]@[ip]:[tujuan]`
* **Contoh Penggunaan:**
```bash
scp data.zip root@192.168.1.50:/home/
```

### 8. `watch`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Menjalankan perintah secara berkala dan menampilkan hasilnya secara real-time.
* **Sintaks:** `watch [perintah]`
* **Contoh Penggunaan:**
```bash
watch -n 1 'df -h'
# Memantau kapasitas disk setiap 1 detik secara otomatis
```

### 9. `iptables`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Mengonfigurasi aturan firewall (paket filtering) kernel Linux.
* **Sintaks:** `sudo iptables -L`
* **Contoh Penggunaan:**
```bash
sudo iptables -L -v -n
# Menampilkan aturan firewall dengan detail trafik
```

### 10. `diff`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Membandingkan dua file teks baris demi baris.
* **Sintaks:** `diff [file1] [file2]`
* **Contoh Penggunaan:**
```bash
diff v1.txt v2.txt
# Menampilkan perbedaan antara file v1 dan v2
```

### 11. `umount`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Melepaskan (unmount) media penyimpanan yang sedang terhubung.
* **Sintaks:** `sudo umount [direktori / perangkat]`
* **Contoh Penggunaan:**
```bash
sudo umount /mnt/usb
```

### 12. `dig`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Melakukan query DNS lookup untuk mendiagnosis masalah server DNS.
* **Sintaks:** `dig [domain]`
* **Contoh Penggunaan:**
```bash
dig ubuntu.com +noall +answer
# Mengambil alamat IP domain ubuntu.com secara spesifik
```

### 13. `cut`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Memotong bagian tertentu dari setiap baris file berdasarkan delimiter.
* **Sintaks:** `cut -d'[pembatas]' -f[kolom] [file]`
* **Contoh Penggunaan:**
```bash
cut -d':' -f1 /etc/passwd
# Menampilkan daftar username system dari file passwd
```

### 14. `vmstat`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Melaporkan informasi statistik memori virtual, proses, CPU, dan I/O disk.
* **Sintaks:** `vmstat [interval] [hitung]`
* **Contoh Penggunaan:**
```bash
vmstat 2 5
# Melaporkan statistik setiap 2 detik sebanyak 5 kali
```

### 15. `dd`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Menyalin dan mengonversi file mentah (biasanya untuk membuat bootable USB ISO).
* **Sintaks:** `sudo dd if=[file.iso] of=[perangkat] bs=4M status=progress`
* **Contoh Penggunaan:**
```bash
sudo dd if=ubuntu.iso of=/dev/sdb bs=4M status=progress
```

### 16. `ncdu`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Analisis penggunaan ruang disk interaktif berbasis ncurses.
* **Sintaks:** `ncdu [direktori]`
* **Contoh Penggunaan:**
```bash
ncdu /home
# Menganalisis folder terbesar secara interaktif
```

### 17. `awk`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Bahasa pemograman pola dan pemindaian teks untuk memproses kolom/baris data.
* **Sintaks:** `awk '{print $[kolom]}' [nama_file]`
* **Contoh Penggunaan:**
```bash
awk '{print $1}' catatan.txt
# Menampilkan kata/kolom pertama dari setiap baris
```

### 18. `nmap`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Pemindai port jaringan dan alat audit keamanan sistem.
* **Sintaks:** `nmap [opsi] [target_ip]`
* **Contoh Penggunaan:**
```bash
nmap -sV 192.168.1.1
# Memindai port terbuka dan versi layanan target
```

### 19. `lsblk`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Menampilkan informasi perangkat blok dalam bentuk struktur pohon (tree).
* **Sintaks:** `lsblk`
* **Contoh Penggunaan:**
```bash
lsblk
```

### 20. `htop`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Menampilkan interaktif process viewer dengan antarmuka warna berbasis teks.
* **Sintaks:** `htop`
* **Contoh Penggunaan:**
```bash
htop
# Gunakan tombol F10 untuk keluar, F9 untuk kill proses.
```

### 21. `env`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Menampilkan daftar seluruh variabel lingkungan yang sedang aktif.
* **Sintaks:** `env`
* **Contoh Penggunaan:**
```bash
env
```

### 22. `rev`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Membalik urutan karakter pada setiap baris teks secara horizontal.
* **Sintaks:** `rev [nama_file]`
* **Contoh Penggunaan:**
```bash
echo 'linux' | rev
# Output: xunil
```

### 23. `fdisk`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Utilitas manipulasi tabel partisi disk berbasis MBR/GPT.
* **Sintaks:** `sudo fdisk -l`
* **Contoh Penggunaan:**
```bash
sudo fdisk -l
# Menampilkan seluruh daftar partisi hard disk yang terdeteksi
```

### 24. `timeout`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Menjalankan perintah dengan batasan waktu maksimal tertentu.
* **Sintaks:** `timeout [durasi] [perintah]`
* **Contoh Penggunaan:**
```bash
timeout 10s ping google.com
# Menjalankan ping hanya selama 10 detik lalu berhenti otomatis
```

### 25. `at`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Menjadwalkan eksekusi perintah satu kali pada waktu tertentu di masa depan.
* **Sintaks:** `echo '[perintah]' | at [waktu]`
* **Contoh Penggunaan:**
```bash
echo 'apt update' | at 02:00
```

### 26. `mount`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Menghubungkan media penyimpanan (partisi, USB, ISO) ke sistem file direktori.
* **Sintaks:** `sudo mount [perangkat] [direktori]`
* **Contoh Penggunaan:**
```bash
sudo mount /dev/sdb1 /mnt/usb
```

### 27. `ssh`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Melakukan remote login aman ke server lain berbasis protokol SSH.
* **Sintaks:** `ssh [username]@[alamat_ip]`
* **Contoh Penggunaan:**
```bash
ssh admin@192.168.1.100
```

### 28. `netstat`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Menampilkan koneksi jaringan, tabel routing, statistik interface, dan koneksi masquerade.
* **Sintaks:** `netstat -rn`
* **Contoh Penggunaan:**
```bash
netstat -anp
# Menampilkan semua koneksi socket beserta program yang menggunakannya
```

### 29. `nslookup`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Alat interaktif untuk melakukan kueri nama server DNS.
* **Sintaks:** `nslookup [domain]`
* **Contoh Penggunaan:**
```bash
nslookup github.com
```

### 30. `export`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Mengatur variabel lingkungan (environment variable) sesi terminal.
* **Sintaks:** `export [NAMA_VAR]=[nilai]`
* **Contoh Penggunaan:**
```bash
export PATH=$PATH:/opt/bin
```

### 31. `xargs`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Membangun dan mengeksekusi perintah dari standar input (pipa data).
* **Sintaks:** `find . -name '*.tmp' | xargs rm`
* **Contoh Penggunaan:**
```bash
find . -name '*.log' | xargs rm -f
# Menghapus seluruh file log yang ditemukan secara paralel
```

### 32. `tune2fs`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Mengubah parameter sistem file ext2/ext3/ext4.
* **Sintaks:** `sudo tune2fs -l [partisi]`
* **Contoh Penggunaan:**
```bash
sudo tune2fs -l /dev/sda1
```

### 33. `blkid`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Menampilkan atribut UUID dan tipe sistem file dari partisi perangkat blok.
* **Sintaks:** `sudo blkid`
* **Contoh Penggunaan:**
```bash
sudo blkid
```

### 34. `alias`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Membuat pintasan (shortcut) nama perintah kustom di terminal.
* **Sintaks:** `alias [nama]='[perintah_panjang]'`
* **Contoh Penggunaan:**
```bash
alias update='sudo apt update && sudo apt upgrade -y'
```

### 35. `sort`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Mengurutkan baris dari file teks.
* **Sintaks:** `sort [opsi] [nama_file]`
* **Contoh Penggunaan:**
```bash
sort -r daftar_nama.txt
# Mengurutkan baris secara terbalik (Z-A)
```

### 36. `logger`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Memasukkan pesan teks kustom langsung ke dalam file log sistem (syslog).
* **Sintaks:** `logger [pesan]`
* **Contoh Penggunaan:**
```bash
logger 'Peringatan: Skrip backup otomatis telah selesai dijalankan.'
```

### 37. `basename`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Mengekstrak nama file murni dari path direktori.
* **Sintaks:** `basename [path]`
* **Contoh Penggunaan:**
```bash
basename /home/user/dokumen/laporan.pdf
```

### 38. `renice`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Mengubah prioritas (niceness) dari proses yang sedang berjalan.
* **Sintaks:** `renice [prioritas] -p [PID]`
* **Contoh Penggunaan:**
```bash
renice 10 -p 4521
# Menurunkan prioritas proses PID 4521 agar tidak memonopoli CPU
```

### 39. `rsync`
* **Kategori:** Jaringan & Diagnostik
* **Fungsi:** Sinkronisasi file dan folder yang sangat cepat dan efisien secara lokal maupun jarak jauh.
* **Sintaks:** `rsync -avz [sumber] [tujuan]`
* **Contoh Penggunaan:**
```bash
rsync -avz /var/www/html/ remote_user@server:/backup/
```

### 40. `duf`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Alternatif modern perintah df yang lebih berwarna dan ramah pengguna untuk cek disk.
* **Sintaks:** `duf`
* **Contoh Penggunaan:**
```bash
duf
```

### 41. `strace`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Melacak system calls dan sinyal yang diterima oleh proses tertentu untuk debugging.
* **Sintaks:** `strace -p [PID]`
* **Contoh Penggunaan:**
```bash
strace -p 1289
```

### 42. `mkfs`
* **Kategori:** Manajemen Sistem File
* **Fungsi:** Membuat sistem file baru (format partisi) di dalam sebuah partisi disk.
* **Sintaks:** `sudo mkfs -t [tipe] [partisi]`
* **Contoh Penggunaan:**
```bash
sudo mkfs -t ext4 /dev/sdb1
# Memformat partisi sdb1 menjadi ekstensi ext4
```

### 43. `dmesg`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Menampilkan pesan buffer dari kernel Linux saat proses booting atau berjalan.
* **Sintaks:** `dmesg | grep [keyword]`
* **Contoh Penggunaan:**
```bash
dmesg | grep -i usb
# Melihat log kernel terkait perangkat USB yang terhubung
```

### 44. `sysctl`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Melihat atau mengubah parameter kernel Linux secara dinamis saat runtime.
* **Sintaks:** `sysctl [opsi] [variabel]`
* **Contoh Penggunaan:**
```bash
sysctl -a
# Menampilkan seluruh variabel kernel yang aktif
```

### 45. `uniq`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Menghilangkan atau melaporkan baris duplikat yang berurutan.
* **Sintaks:** `uniq [opsi] [nama_file]`
* **Contoh Penggunaan:**
```bash
sort angka.txt | uniq -c
# Mengurutkan lalu menghitung frekuensi kemunculan angka unik
```

### 46. `tr`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Menerjemahkan, meremas, dan/atau menghapus karakter dari standar input.
* **Sintaks:** `tr [set1] [set2]`
* **Contoh Penggunaan:**
```bash
cat file.txt | tr 'a-z' 'A-Z'
# Mengubah seluruh teks kecil menjadi huruf kapital
```

### 47. `paste`
* **Kategori:** Manipulasi Teks & Pemrosesan Data
* **Fungsi:** Menggabungkan baris dari beberapa file secara berdampingan.
* **Sintaks:** `paste [file1] [file2]`
* **Contoh Penggunaan:**
```bash
paste kolom1.txt kolom2.txt
```

### 48. `pkill`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Menghentikan proses berdasarkan nama atau pola string secara langsung.
* **Sintaks:** `pkill [nama_proses]`
* **Contoh Penggunaan:**
```bash
pkill -u budi
# Menghentikan semua proses yang berjalan atas nama user 'budi'
```

### 49. `journalctl`
* **Kategori:** Manajemen Proses & Sistem
* **Fungsi:** Membaca log dari systemd journal secara komprehensif.
* **Sintaks:** `journalctl -u [nama_layanan]`
* **Contoh Penggunaan:**
```bash
journalctl -u nginx.service -b
# Melihat log layanan Nginx sejak booting terakhir
```

### 50. `crontab`
* **Kategori:** Utilitas & Skrip
* **Fungsi:** Mengatur penjadwalan tugas otomatis (cron jobs) di latar belakang sistem.
* **Sintaks:** `crontab -e`
* **Contoh Penggunaan:**
```bash
crontab -e
# Mengedit daftar jadwal tugas rutin harian/mingguan
```

