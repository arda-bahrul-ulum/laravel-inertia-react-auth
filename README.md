# Laravel Inertia React Auth

Sistem ini adalah aplikasi autentikasi sederhana berbasis Laravel (backend) dan React (frontend) yang terintegrasi menggunakan Inertia.js. Proyek ini cocok sebagai boilerplate atau pembelajaran untuk membangun aplikasi modern dengan stack Laravel + React tanpa perlu API RESTful secara terpisah.

## Deskripsi Sistem

Aplikasi ini menyediakan fitur:

-   **Registrasi pengguna** (Register)
-   **Login dan Logout**
-   **Dashboard** setelah login
-   **Proteksi halaman** menggunakan middleware Laravel
-   **Navigasi SPA** (Single Page Application) dengan Inertia.js
-   **Notifikasi error** pada proses login/registrasi

### Alur Autentikasi

1. **Register**: Pengguna mendaftar melalui form, data dikirim ke backend Laravel, divalidasi, dan disimpan ke database.
2. **Login**: Pengguna mengisi email & password, backend memverifikasi kredensial, dan membuat session.
3. **Dashboard**: Setelah login, pengguna diarahkan ke halaman dashboard.
4. **Logout**: Session dihapus, pengguna diarahkan ke halaman login.

## Stack & Library yang Digunakan

### Backend (Laravel)

-   **Laravel Framework** ^9.19
-   **PHP** ^8.0.2
-   **inertiajs/inertia-laravel**: Integrasi Inertia di Laravel
-   **laravel/sanctum**: Opsi untuk API token (tidak wajib untuk SPA)
-   **guzzlehttp/guzzle**: HTTP client
-   **laravel/tinker**: REPL untuk Laravel

### Frontend (React)

-   **React** ^17.0.2
-   **@inertiajs/inertia**: Library utama Inertia
-   **@inertiajs/inertia-react**: Adapter React untuk Inertia
-   **@inertiajs/progress**: Progress bar SPA
-   **axios**: HTTP client (jika dibutuhkan)
-   **lodash**: Utility library
-   **vite**: Build tool modern untuk frontend
-   **laravel-vite-plugin**: Integrasi Vite dengan Laravel

## Struktur Folder Penting

-   `app/Http/Controllers/Auth/`: Controller untuk login, register, logout
-   `resources/js/Pages/`: Halaman React (Login, Register, Dashboard)
-   `resources/js/Layouts/`: Layout utama React
-   `routes/web.php`: Routing utama Laravel
-   `resources/js/app.jsx`: Entry point React + Inertia

## Cara Instalasi

### 1. Clone Repository

```bash
git clone <repo-url>
cd laravel-inertia-react-auth
```

### 2. Install Dependency Backend (Laravel)

```bash
composer install
```

### 3. Install Dependency Frontend (React)

```bash
npm install
# atau
yarn install
```

### 4. Konfigurasi Environment

Copy file `.env.example` menjadi `.env` lalu atur koneksi database dan konfigurasi lain sesuai kebutuhan.

```bash
cp .env.example .env
```

Generate app key:

```bash
php artisan key:generate
```

### 5. Migrasi Database

```bash
php artisan migrate
```

### 6. Menjalankan Server

#### Backend (Laravel)

```bash
php artisan serve
```

#### Frontend (Vite)

```bash
npm run dev
# atau
yarn dev
```

Akses aplikasi di `http://localhost:8000` (atau sesuai output artisan serve).

## Fitur Halaman

-   `/register` — Halaman registrasi
-   `/login` — Halaman login
-   `/dashboard` — Dashboard (hanya untuk user yang sudah login)

## Lisensi

MIT License.
