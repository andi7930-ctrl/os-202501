
# Laporan Praktikum Minggu [X]
Topik: "Arsitektur Sistem Operasi dan Kernel"

---

## Identitas
- **Nama**  : ANDI PRATAMA 
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
uname -a
lsmod | head
dmesg | head
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![alt text](<screenshot/Screenshot (14).png>)

---

## Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  
-Jelaskan makna hasil percobaan.

Uname -a:
sedang menggunakan sistem operasi Linux yang diberi nama DESKTOP-OHDCE0G. Kernel (inti) Linux yang Anda gunakan adalah versi 6.6.87.2, dan yang paling penting, ini adalah kernel khusus yang dibuat oleh Microsoft untuk menjalankan Linux di dalam Windows menggunakan teknologi WSL2 (Windows Subsystem for Linux 2).
Whoami :
Saat saya mengetik whoami di terminal, komputer akan langsung menjawab dengan nama akun yang sedang saya gunakan saat itu.
lsmod | head
saya menggunakan lsmod | head untuk mendapatkan gambaran cepat tentang modul-modul apa saja yang dimuat tanpa harus melihat seluruh daftar panjang yang mungkin mencapai ratusan baris.
dmesg | head
Komando ini adalah cara yang efektif (meskipun agak berlebihan dengan | head kedua) untuk melihat 10 log kernel sistem yang pertama saat booting. Ini sering digunakan untuk mencari informasi dasar tentang kernel, CPU, atau perangkat keras yang terdeteksi pertama

Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).
Kernel adalah inti dari sistem operasi, berfungsi sebagai jembatan antara perangkat keras (hardware) dan program aplikasi. Versi yang tercantum menunjukkan pengelola sumber daya utama—CPU, memori, dan perangkat I/O—yang dirancang khusus oleh Microsoft untuk berjalan di atas Windows (WSL2) untuk menyediakan lingkungan Linux.
System Call adalah cara bagi program aplikasi untuk meminta layanan dari kernel (misalnya, meminta akses file atau membuat proses baru). Keberadaan nama Linux menegaskan bahwa sistem ini menggunakan API Linux (Application Programming Interface), yang mendefinisikan set System Call standar Linux.
Ini menunjukkan sistem beroperasi dalam Arsitektur Hibrida/Virtualisasi. WSL2 menggunakan mesin virtual (VM) ringan untuk menjalankan kernel Linux secara independen di atas hypervisor Windows. Ini bukan arsitektur monolitik atau microkernel murni, melainkan solusi virtualisasi untuk mencapai kompatibilitas Linux penuh di Windows.

Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?
LINUX :wiHasil ini menunjukkan sistem operasi independen tanpa lapisan virtualisasi.
WINOWS :Hasilnya fokus pada nama akun lokal di sistem Linux tersebut.


---

## Kesimpulan
1. Identitas Unik OS
-Linux yang divirtualisasikan di atas Windows.
3. Peran Kernel dan Pengguna
-Pengguna (whoami) berinteraksi dengan sistem menggunakan antarmuka (terminal).
5. Adopsi Arsitektur Hibrida
-Sistem ini tidak mengikuti arsitektur monolitik atau microkernel murni.
---

## Quiz
1. [Sebutkan tiga fungsi utama sistem operasi.]  
   **Jawaban:
   1. Manajemen Sumber Daya
   2. Antarmuka Pengguna
   3.  Penyediaan Layanan Sistem**  
3. [Jelaskan perbedaan antara kernel mode dan user mode.]  
   **Jawaban:
   Kernel Mode adalah pemerintah pusat. Ia memiliki akses penuh dan tidak terbatas ke semua sumber daya sistem, termasuk CPU, memori, dan semua perangkat keras (hard disk, keyboard, printer).
   User Mode adalah warga negara. Ia memiliki hak istimewa yang terbatas. **  
5. [Sebutkan contoh OS dengan arsitektur monolithic dan microkernel.]  
   **Jawaban:
   -Contoh OS Monolithic:
Linux (Kernel GNU/Linux)
UNIX Tradisional (termasuk varian lama seperti BSD)
MS-DOS
Windows 9x (Windows 95, 98, Me)
-Contoh OS Microkernel:
MINIX (dibuat oleh Andrew S. Tanenbaum untuk tujuan edukasi)
QNX (sering digunakan pada sistem embedded dan real-time karena stabilitasnya yang tinggi)
Mach (digunakan sebagai dasar untuk kernel-kernel berikutnya, termasuk di NeXTSTEP)
Symbian OS (OS yang populer di ponsel pintar awal)

**  

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?
  >Belum sepenuhnya memahami materi mata kuliah 
- Bagaimana cara Anda mengatasinya?
  >Perlu mempelajari matkul yang belum paham di luar jam kuliah

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
