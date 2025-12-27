# Laporan Praktikum 4 - Laravel Breeze Authentication

## Identitas Mahasiswa
- **Nama:** Arkan Ibnu Pandegi  
- **NPM:** 4522210097  
- **Mata Kuliah:** Pemrograman Berbasis Web  
- **Materi:** Autentikasi Laravel Breeze  

---

## Deskripsi Proyek
**LaraPress** adalah proyek Laravel yang mengimplementasikan sistem autentikasi menggunakan **Laravel Breeze**.  
Proyek ini mencakup instalasi, konfigurasi, dan modifikasi route untuk langsung menampilkan halaman login serta manajemen posts.

---

## Materi Praktikum

### 1. Instalasi Laravel Breeze

**Langkah-langkah:**

1. **Install Laravel Breeze via Composer**
   ```bash
   composer require laravel/breeze --dev


2. **Install Breeze Stack**
     ```bash
     php artisan breeze:install
Aplikasi berjalan di http://localhost:8000.

3. **Modifikasi Route untuk Langsung ke Halaman Login**
     ```bash
     Route::get('/', function () {
    return view('auth.login');
});

4. Route yang Diimplementasikan

Route Publik:

/ → Menampilkan halaman login

Route Autentikasi (Protected):

/dashboard → Halaman dashboard (memerlukan autentikasi & verifikasi email)

/profile → Menampilkan form edit profil

/profile (PATCH) → Update profil user

/profile (DELETE) → Hapus akun user

Route Posts Management (Protected):

/posts/create → Form create post baru

/posts (POST) → Menyimpan post baru

/posts/{post}/edit → Form edit post

/posts/{post} (PUT) → Update post

/posts/{post} (DELETE) → Hapus post

5. Fitur-Fitur Laravel Breeze

Login → Halaman login user

Register → Halaman registrasi user baru

Password Reset → Reset password via email

Email Verification → Verifikasi email (aktif pada route dashboard)

Profile Management → Update profil user

Password Confirmation → Konfirmasi password untuk aksi sensitif

6. Struktur File Autentikasi

app/Http/Controllers/Auth/* → Controller autentikasi

resources/views/auth/* → View login, register, dll

resources/views/layouts/* → Layout aplikasi

resources/views/profile/* → Halaman profil user

routes/auth.php → Route khusus autentikasi


7. **Middleware yang Digunakan**
    ```bash
    Route::middleware('auth')->group(function () {
    // Route yang dilindungi
});


8. Cara Kerja Aplikasi

Akses Pertama Kali:
User mengakses http://localhost:8000 → langsung menampilkan halaman login

Registrasi:
User baru bisa registrasi melalui link di halaman login → login otomatis setelah registrasi

Login:
User memasukkan email & password → diarahkan ke dashboard jika berhasil login

Dashboard:
Hanya bisa diakses user yang sudah login & terverifikasi → menampilkan info user & navigasi fitur lain

Manajemen Posts:
User dapat membuat, mengedit, dan menghapus posts → semua operasi memerlukan autentikasi

9. Hasil Running :
    <img width="1028" height="610" alt="image" src="https://github.com/user-attachments/assets/ade7496f-8316-4653-a029-de5d417cad41" />


✅ Halaman login muncul langsung saat mengakses http://localhost:8000

✅ User dapat registrasi akun baru

✅ Setelah login, user diarahkan ke dashboard

✅ User dapat mengakses halaman profil untuk update informasi

✅ User dapat melakukan CRUD operations pada posts

✅ Dashboard dilindungi middleware auth & verified

Kesimpulan

Laravel Breeze menyediakan scaffold autentikasi minimal dan sederhana, cocok untuk memulai proyek baru dengan fitur autentikasi lengkap.
Dengan memodifikasi route menggunakan return view('auth.login'), user langsung melihat halaman login saat mengakses aplikasi tanpa redirect tambahan.
Proyek ini juga telah dilengkapi fitur manajemen posts yang dilindungi autentikasi.
   


    

   
