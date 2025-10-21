
# Laporan Praktikum Minggu [X]
Topik: Manajemen File dan Permission di Linux



---

## Identitas
- **Nama**  : Andi Pratama  
- **NIM**   : 250202975  
- **Kelas** : 1IKRA

---

## Tujuan
Tuliskan tujuan praktikum minggu ini.  
Contoh:  
Praktikum Manajemen File dan Permission di Linux bertujuan agar peserta dapat memahami struktur sistem file Linux secara menyeluruh, mulai dari direktori root hingga berbagai subdirektori dan file yang ada di dalamnya. Selain itu, peserta diharapkan mampu menguasai perintah dasar untuk mengelola file dan direktori, seperti ls, cp, mv, rm, mkdir, dan rmdir, sehingga dapat melakukan manipulasi file dengan efektif. Praktikum ini juga menekankan pemahaman konsep hak akses atau permission yang terdiri dari izin baca, tulis, dan eksekusi untuk pemilik (owner), grup, dan pengguna lain (others). Dengan demikian, peserta dapat menggunakan perintah chmod untuk mengubah permission, serta chown dan chgrp untuk mengatur pemilik dan grup file atau direktori. Pengaturan hak akses ini sangat penting dalam menjaga keamanan sistem dan data, sehingga peserta juga belajar bagaimana menghindari konfigurasi yang dapat menimbulkan risiko keamanan. Selain itu, peserta dilatih menggunakan perintah find untuk mencari file berdasarkan permission tertentu dan memanfaatkan opsi pada perintah ls untuk menampilkan detail permission. Praktikum ini juga mengenalkan konsep tautan (link), baik hard link maupun symbolic link, serta bagaimana membuat dan mengelolanya menggunakan perintah ln. Dengan tujuan-tujuan tersebut, diharapkan peserta dapat mengelola file dan izin akses secara aman dan efisien dalam lingkungan sistem operasi Linux.

---

## Dasar Teori
Tuliskan ringkasan teori (3–5 poin) yang mendasari percobaan.

1.Struktur Sistem File Linux
Linux menggunakan struktur sistem file berbentuk hierarki pohon dengan direktori root (/) sebagai titik awal. Semua file dan direktori berada di bawah root, yang memudahkan pengorganisasian dan akses data.

2.Konsep Permission pada File dan Direktori
Setiap file dan direktori di Linux memiliki tiga jenis izin akses yang berbeda untuk tiga kategori pengguna: pemilik (owner), grup (group), dan pengguna lain (others). Izin tersebut meliputi read (r), write (w), dan execute (x).

3.Perintah untuk Mengatur Permission dan Kepemilikan
Perintah chmod digunakan untuk mengubah hak akses file atau direktori, sementara chown dan chgrp digunakan untuk mengubah pemilik dan grup dari file atau direktori tersebut.

4.Manajemen File Dasar di Linux
Perintah seperti ls, cp, mv, rm, dan mkdir digunakan untuk melihat, menyalin, memindahkan, menghapus, dan membuat file atau direktori dalam sistem Linux.

5.Penggunaan Link dalam Sistem File
Linux mendukung hard link dan symbolic link yang memungkinkan satu file atau direktori memiliki lebih dari satu nama atau jalur, sehingga mempermudah pengelolaan file tanpa duplikasi data.
---

## Langkah Praktikum
## C. Langkah Pengerjaan
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

5. **Eksperimen 4 – Dokumentasi**
   - Ambil screenshot hasil terminal dan simpan di:
     ```
     praktikum/week3-linux-fs-permission/screenshots/
     ```
   - Tambahkan analisis hasil pada `laporan.md`.

6. **Commit & Push**
   ```bash
   git add .
   git commit -m "Minggu 3 - Linux File System & Permission"
   git push origin main
   ```.

---

## Kode / Perintah
Tuliskan potongan kode atau perintah utama:
```bash
uname -a
lsmod | head
dmesg | head
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](screenshots/example.png)

---

## Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  

---

## Kesimpulan
Tuliskan 2–3 poin kesimpulan dari praktikum ini.

---

## Quiz
1. [Pertanyaan 1]  
   **Jawaban:**  
2. [Pertanyaan 2]  
   **Jawaban:**  
3. [Pertanyaan 3]  
   **Jawaban:**  

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
