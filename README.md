Nama : Alfido Mazdan Marsyadi
NIM  : H1D022084
Shift B

**Screenshot**
![image](https://github.com/user-attachments/assets/2013a570-934e-4b33-91a5-d7302c884bd5)

![{DA2D7E7E-EF4C-4386-8A73-DA36635A8774}](https://github.com/user-attachments/assets/148aa131-2db0-4d06-9ff0-0aa7b5db7004)

**Penjelasan**
Berikut adalah penjelasan tentang cara kerja login:

### Tahap Input:
1. Pengguna memasukkan username dan password pada form login.
2. Aplikasi melakukan validasi awal untuk memastikan tidak ada input yang kosong.
3. Jika ada input yang kosong, aplikasi akan menampilkan pesan kesalahan.

### Tahap Pengiriman Data:
1. Data username dan password dikirim ke server melalui metode HTTP POST.
2. Data dikirim dalam format JSON.

### Tahap Pemrosesan di Server:
1. Server menerima data login yang dikirim.
2. Password akan di-hash menggunakan algoritma MD5 untuk keamanan.
3. Server memeriksa data tersebut pada database.
4. Jika data yang dimasukkan valid, server akan menghasilkan token unik.
5. Server mengirimkan response berisi status login, token, dan username.

### Tahap Penanganan Response:
1. Aplikasi menerima response dari server.
2. Jika login berhasil:
   - Token dan username disimpan dalam penyimpanan lokal.
   - Status autentikasi diperbarui.
   - Pengguna diarahkan ke halaman utama.
3. Jika login gagal:
   - Pesan kesalahan ditampilkan.
   - Pengguna tetap berada di halaman login.

### Tahap Penyimpanan Session:
1. Token dan username disimpan di penyimpanan lokal (seperti SharedPreferences).
2. Data ini digunakan untuk:
   - Memeriksa status login pengguna.
   - Mempertahankan sesi login.
   - Mengakses halaman yang memerlukan autentikasi.

### Pengamanan:
1. Password akan di-hash sebelum disimpan.
2. Token digunakan untuk verifikasi pengguna.
3. Terdapat pengamanan di sisi routing dengan guard.
4. Validasi input untuk mencegah pengiriman data kosong.
5. Server menangani masalah CORS (Cross-Origin Resource Sharing).

### Fitur Tambahan:
1. Auto login jika sesi masih aktif.
2. Notifikasi untuk berbagai status login.
3. Pengalihan otomatis berdasarkan status autentikasi.
4. Fitur logout untuk mengakhiri sesi pengguna.
