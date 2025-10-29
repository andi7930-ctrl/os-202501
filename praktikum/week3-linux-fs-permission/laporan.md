
# Laporan Praktikum Minggu [X]
Topik: Manajemen File dan Permission di Linux



---

## Identitas
- **Nama**  : Andi Pratama  
- **NIM**   : 250202975  
- **Kelas** : 1IKRA

---

## Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

1. Menggunakan perintah `ls`, `pwd`, `cd`, `cat` untuk navigasi file dan direktori.
2. Menggunakan `chmod` dan `chown` untuk manajemen hak akses file.
3. Menjelaskan hasil output dari perintah Linux dasar.
4. Menyusun laporan praktikum dengan struktur yang benar.

---

## Dasar Teori
Tujuan utama dari praktikum ini adalah untuk mengoperasikan perintah Linux dasar dengan benar, serta memahami sistem izin (permission). Dalam sistem operasi Linux, setiap aktivitas pengguna hampir selalu berkaitan dengan pengelolaan file dan direktori. Untuk itu, penting memahami beberapa perintah dasar seperti `pwd`, `ls -l`, `cat`, `head`, `chmod`, dan `chown`. Keseluruhan konsep ini menjadi dasar penting bagi setiap pengguna untuk memahami cara kerja Linux secara lebih mendalam dan bertanggung jawab terhadap keamanan sistem.

---

## Langkah Praktikum
1. **Setup Environment**
   - Gunakan Linux (Ubuntu/WSL).
   - Pastikan folder kerja berada di dalam direktori repositori Git praktikum:
     ```
     praktikum/week3-linux-fs-permission/
     ```

2. **Eksperimen 1 – Navigasi Sistem File**
   Jalankan perintah berikut:
   ```bash
   pwd
   ls -l
   cd /tmp
   ls -a
   ```
   - Jelaskan hasil tiap perintah.
   - Catat direktori aktif, isi folder, dan file tersembunyi (jika ada).

3. **Eksperimen 2 – Membaca File**
   Jalankan perintah:
   ```bash
   cat /etc/passwd | head -n 5
   ```
   - Jelaskan isi file dan struktur barisnya (user, UID, GID, home, shell).

4. **Eksperimen 3 – Permission & Ownership**
   Buat file baru:
   ```bash
   echo "Hello <NAME><NIM>" > percobaan.txt
   ls -l percobaan.txt
   chmod 600 percobaan.txt
   ls -l percobaan.txt
   ```
   - Analisis perbedaan sebelum dan sesudah chmod.  
   - Ubah pemilik file (jika memiliki izin sudo):
   ```bash
   sudo chown root percobaan.txt
   ls -l percobaan.txt
   ```
   - Catat hasilnya.

---

## Kode / Perintah
Potongan kode atau perintah utama:

Eksperimen 1
```bash
pwd
ls -l
cd /tmp
ls -a
```
Eksperimen 2
```bash
cat /etc/passwd | head -n 5
```
Eksperimen 3
```bash
echo "Hello <RIZKY IQBAL HISYAM><250202926>" > percobaan.txt
ls -l percobaan.txt
chmod 600 percobaan.txt
ls -l percobaan.txt

sudo chown root percobaan.txt
ls -l percobaan.txt
```

---

## Hasil Eksekusi
Screenshot hasil percobaan:
![alt text](<screenshots/eksperimen.png>)


---


## Tugas & Quiz
**Tugas Analisis Hasil Eksperimen**

### 1. Eksperimen navigasi sistem file

| **No** | **Perintah** | **Output / Hasil** | **Analisis / Penjelasan** | **Sumber Referensi** |
|:--:|:----------------|:-------------------|:---------------------------|:---------------------|
| 1 | `pwd` | `/home/andipratama-250202975/os-202501` | Menampilkan direktori kerja (working directory) saat ini. Artinya pengguna sedang berada di folder proyek bernama `os-202501-250202975`. | Abraham Silberschatz, *Operating System Concepts*, 10th Ed., Wiley, 2018. |
| 2 | `ls -l` | `LICENSE`, `README.md`, `docs`, `praktikum` | Menampilkan isi folder aktif secara detail (satu item per baris). File dan folder tersebut berisi dokumentasi serta data tugas praktikum. | Andrew S. Tanenbaum, *Modern Operating Systems*, 4th Ed., Pearson, 2015. |
| 3 | `cd /tmp` | *(tidak ada output)* | Perintah `cd` digunakan untuk berpindah direktori. Setelah perintah ini dijalankan, direktori aktif berpindah dari `/home/...` ke `/tmp`. | *Linux Manual Pages* — `man cd`. |
| 4 | `ls -a` | `.`, `..`, `.X11-unix`, `snap-private-tmp`, `systemd-private-*` | Menampilkan semua isi direktori `/tmp`, termasuk file tersembunyi (diawali titik `.`). Folder `.X11-unix` digunakan oleh sistem grafis X11, sedangkan `systemd-private-*` adalah direktori sementara yang dibuat layanan sistem untuk menjaga keamanan dan isolasi proses. | *Linux Manual Pages* — `man ls`; *Systemd Documentation* (freedesktop.org). |


### 2. Eksperimen membaca file


| No | Username | UID | GID | Home Directory | Shell              | Keterangan                                                                 |
|----|----------|-----|-----|----------------|---------------------|------------------------------------------------------------------------------|
| 1  | root     | 0   | 0   | /root          | /bin/bash           | Akun superuser dengan hak penuh untuk mengelola sistem.                     |
| 2  | daemon   | 1   | 1   | /usr/sbin      | /usr/sbin/nologin   | Akun sistem yang menjalankan proses daemon, tidak dapat login.              |
| 3  | bin      | 2   | 2   | /bin           | /usr/sbin/nologin   | Akun sistem untuk kepemilikan file biner penting.                           |
| 4  | sys      | 3   | 3   | /dev           | /usr/sbin/nologin   | Akun sistem yang digunakan oleh layanan internal sistem operasi.            |
| 5  | sync     | 4   | 65534| /bin          | /bin/sync           | Akun khusus untuk sinkronisasi data ke disk, biasanya digunakan saat recovery. |



### 3. Eksperimen permission & ownership

| No | Perintah yang Dijalankan | Hasil / Output (`ls -l`) | Analisis / Keterangan | Referensi |
|----|---------------------------|--------------------------|------------------------|------------|
| 1 | `echo "Hello <ANDI PRATAMA><250202975>" > percobaan.txt` | *File baru dibuat* | Membuat file teks baru bernama `percobaan.txt` dengan isi teks tertentu. Pemilik awal adalah user yang sedang login. | Shotts, *The Linux Command Line*, 2019 |
| 2 | `ls -l percobaan.txt` | `-rw-r--r-- 1 andi andi 38 Oct 20 22:07 percobaan.txt` | Permission default (`rw-r--r--` / 644) menunjukkan bahwa pemilik dapat membaca dan menulis, sedangkan group dan others hanya dapat membaca. | GNU Coreutils Manual – `ls` |
| 3 | `chmod 600 percobaan.txt` | *Tidak ada output (izin berubah)* | Mengubah mode akses menjadi `600` (`rw-------`), artinya hanya pemilik file yang dapat membaca dan menulis. | Tanenbaum, *Modern Operating Systems*, 2015 |
| 4 | `ls -l percobaan.txt` | `-rw------- andi andi 38 Oct 20 22:07 percobaan.txt` | Hanya user `rizky` yang memiliki akses penuh terhadap file, sedangkan group dan others tidak memiliki akses. | Silberschatz, *Operating System Concepts*, 2018 |
| 5 | `sudo chown root percobaan.txt` | *Tidak ada output (pemilik berubah)* | Mengubah kepemilikan file dari `rizky` menjadi `root`. | Linux Manual Page – `chown(1)` |
| 6 | `ls -l percobaan.txt` | `-rw------- 1 root andi 38 Oct 20 22:07 percobaan.txt` | File kini dimiliki oleh `root`. Karena permission masih `600`, user biasa tidak dapat membaca maupun menulis file tersebut. | Silberschatz, *Operating System Concepts*, 2018 |


**Quiz**
1. Apa fungsi dari perintah `chmod`? 
   
   **Jawaban:** Fungsi `chmod` yaitu untuk mengubah *permission* (hak akses) file atau direktori.

2. Apa arti dari kode permission `rwxr-xr--`?  

   **Jawaban:** berikut penjelasan tiap bagian dari kode `rwxr-xr--`

| Bagian | Arti | Keterangan |
|:--|:--|:--|
| **-** | Jenis file | `-` = file biasa, `d` = direktori, `l` = link |
| **rwx** | Hak akses **user (pemilik)** | Dapat *read (r)*, *write (w)*, dan *execute (x)* |
| **r-x** | Hak akses **group (grup)** | Dapat *read (r)* dan *execute (x)* saja |
| **r--** | Hak akses **others (lainnya)** | Hanya *read (r)* saja |



3. Jelaskan perbedaan antara `chown` dan `chmod`.  

   **Jawaban:** Perintah chmod dan chown adalah dua lapisan kontrol keamanan utama di Linux.
`chmod` memiliki peran dalam mengatur mode/tingkat akses (akses kontrol) terhadap file. Sedangkan `chown` mengatur kepemilikan (ownership) file.
Keduanya memiliki peran untuk mengatur hak akses, menjaga kerahasiaan, dan ketersediaan data dalam sistem.

---
## Kesimpulan
Dari praktikum ini, dapat disimpulkan bahwa:

  * Navigasi dan manipulasi file di lingkungan Linux sangat bergantung pada perintah-perintah dasar seperti `ls`, `cd`, `pwd`, dan `cat`, yang masing-masing memiliki fungsi spesifik untuk berinteraksi dengan sistem file.
  * Keamanan file di Linux diatur secara ketat melalui mekanisme **permission** dan **ownership**. Perintah `chmod` berfungsi untuk mengubah hak akses (baca, tulis, eksekusi), sedangkan `chown` berfungsi untuk mengubah kepemilikan (user dan group).
  * Pemahaman dan penggunaan yang benar atas `chmod` dan `chown` sangat krusial untuk menjaga keamanan dan integritas data dalam sistem operasi multi-user seperti Linux.

---

## Quiz
1.  **Apa fungsi dari perintah `chmod`?**

    **Jawaban:**
    `chmod` adalah singkatakn dari *change mode*. Fungsinya untuk mengubah izin akses / *permissions* sebuah file atau direktori. Perintah ini menentukan siapa saja yang boleh membaca (`r`), menulis (`w`), dan mengeksekusi (`x`) file tersebut, yang berlaku untuk pemilik file, grup, dan pengguna lainnya.

-----

2.  **Apa arti dari kode permission `rwxr-xr--`?**

    **Jawaban:**
    | Kode Perimission | Keterangan |
    | :--- | :--- |
    | `rwx` | Izin untuk Pemilik(*User*). Pemilik file memiliki izin penuh untuk membaca (*read*), menulis (*write*), dan mengeksekusi (*execute*) file tersebut. |
    | `r-x` | Izin untuk Grup. Pengguna yang termasuk dalam grup file ini dapat membaca (*read*) dan mengeksekusi (*execute*), tetapi tidak dapat menulis atau mengubah file. |
    | `r--` | Pengguna lain di luar pemilik dan grup hanya dapat membaca (*read*) file tersebut. |
-----

3.  **Jelaskan perbedaan antara `chown` dan `chmod`.**

    **Jawaban:**
    Perbedaannya terletak pada aspek keamanan yang mereka kontrol
      * `chown` *change owner* mengubah **siapa yang memiliki** file atau direktori. Perintah ini mengatur aspek kepemilikan (user dan group).
      * `chmod` *change mode* mengubah **apa yang dapat dilakukan** terhadap file atau direktori. Perintah ini mengatur aspek izin akses (baca, tulis, eksekusi).


---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?tidak  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
