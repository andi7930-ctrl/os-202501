
# Laporan Praktikum Minggu [X]
Topik: syscall-structures

---

## Identitas
- **Nama**  : Andi pratama   
- **NIM**   : 250202975  
- **Kelas** : 1IKRA

---

## Tujuan
Tuliskan tujuan praktikum minggu ini.  
Contoh:  
> Mahasiswa mampu menjelaskan fungsi utama sistem operasi dan peran kernel serta system call.

---

## Dasar Teori
Tuliskan ringkasan teori (3–5 poin) yang mendasari percobaan.

---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah
Tuliskan potongan kode atau perintah utama:
```bash
strace ls
strace -e trace=open,read,write,close cat /etc/paswwd
dmesg | tail -n10
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![alt text](screenshots/screenshotssyscall_ls.png)
![alt text](screenshots/screenshotssyscall2_ls.png)
![alt text](screenshots/screenshotssyscall3_ls.png)


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
1. Apa fungsi utama system call dalam sistem operasi?  
   **Jawaban:
   1.manajemen proses
   2.manajemen file
   3.komunikasi
   4.manajemen sistem & proteksi**  
3. Sebutkan 4 kategori system call yang umum digunakan. 
   **Jawaban:
   1.proses control
   2.file manajer
   3.Devive management
   4.information maintance & commmuniacation**  
5. Mengapa system call tidak bisa dipanggil langsung oleh user program? 
   **Jawaban:
    karena hanya dapat dijalankan di mode kernel,sedangkan program berjalan di mode user**  

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
