# 📮 LaravelPostman

> **UTS Project** - Platform Manajemen dan Testing API Berbasis Laravel & Postman Integration

[![Laravel](https://img.shields.io/badge/Laravel-v9%2B-FF2D20?style=flat-square&logo=laravel)](https://laravel.com)
[![PHP](https://img.shields.io/badge/PHP-v8.0%2B-777BB4?style=flat-square&logo=php)](https://php.net)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?style=flat-square&logo=javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![MySQL](https://img.shields.io/badge/MySQL-v5.7%2B-4479A1?style=flat-square&logo=mysql)](https://www.mysql.com)
[![Vite](https://img.shields.io/badge/Vite-v4%2B-646CFF?style=flat-square&logo=vite)](https://vitejs.dev)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)

## 📑 Daftar Isi

- [Fitur Utama](#-fitur-utama)
- [Prerequisites](#-prerequisites)
- [Instalasi Cepat](#-instalasi-cepat)
- [Konfigurasi Detail](#-konfigurasi-detail)
- [Struktur Folder](#-struktur-folder)
- [Panduan Penggunaan](#-panduan-penggunaan)
- [API Documentation](#-api-documentation)
- [Database Schema](#-database-schema)
- [Testing](#-testing)
- [Troubleshooting](#-troubleshooting)
- [Deployment](#-deployment)
- [Kontribusi](#-kontribusi)
- [Support](#-support)
- [Lisensi](#-lisensi)

---

## ✨ Fitur Utama

- 🔐 **Autentikasi & Otorisasi** - Sistem login dengan role-based access control
- 📊 **Dashboard Interaktif** - Monitoring API requests dan responses real-time
- 🧪 **API Testing Integration** - Integrasi langsung dengan Postman collections
- 📝 **Request Management** - Buat, edit, dan simpan request templates
- 📈 **Analytics & Logging** - Tracking history dan analytics API calls
- 🎨 **Modern UI** - Interface responsif dengan Tailwind CSS
- ⚡ **Performance Optimized** - Caching dan lazy loading implementation
- 🔄 **Version Control** - Track perubahan dan rollback requests
- 📱 **Mobile Responsive** - Akses dari device apapun
- 🚀 **RESTful API** - Endpoint API yang well-documented

---

## 📦 Prerequisites

Sebelum memulai, pastikan sistem Anda memiliki:

| Requirement | Version | Status |
|-------------|---------|--------|
| **PHP** | `>= 8.0` | ✅ Required |
| **Composer** | Latest | ✅ Required |
| **Node.js** | `>= 14.0` | ✅ Required |
| **npm** | `>= 6.0` | ✅ Required |
| **MySQL** | `>= 5.7` | ✅ Required |
| **Git** | Latest | ✅ Required |

### Check Your System

```bash
# Check PHP version
php -v

# Check Composer
composer --version

# Check Node & npm
node -v
npm -v

# Check MySQL
mysql --version
```

---

## 🚀 Instalasi Cepat

### Step 1: Clone Repository

```bash
git clone https://github.com/ShiniGOD/LaravelPostman.git
cd LaravelPostman
```

### Step 2: Install PHP Dependencies

```bash
composer install
```

### Step 3: Install JavaScript Dependencies

```bash
npm install
```

### Step 4: Setup Environment

```bash
# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate
```

### Step 5: Database Configuration

```bash
# Create database (MySQL command)
mysql -u root -p -e "CREATE DATABASE laravel_postman CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;"

# Run migrations
php artisan migrate

# Seed data (optional)
php artisan db:seed
```

### Step 6: Build Assets

```bash
# Development
npm run dev

# Production
npm run build
```

### Step 7: Start Application

```bash
php artisan serve
```

✅ Aplikasi siap diakses di `http://localhost:8000`

---

## ⚙️ Konfigurasi Detail

### Environment Configuration (`.env`)

Buka file `.env` dan konfigurasi sesuai kebutuhan:

```env
# ============================================
# APPLICATION SETTINGS
# ============================================
APP_NAME="LaravelPostman"
APP_ENV=local
APP_KEY=base64:xxxxxxxxxxxxxxxxxxxxxxxxxxxx
APP_DEBUG=true
APP_URL=http://localhost:8000

# ============================================
# DATABASE CONFIGURATION
# ============================================
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel_postman
DB_USERNAME=root
DB_PASSWORD=

# ============================================
# CACHE & SESSION
# ============================================
CACHE_DRIVER=file
SESSION_DRIVER=file
QUEUE_CONNECTION=sync

# ============================================
# MAIL CONFIGURATION
# ============================================
MAIL_MAILER=log
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=465
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=noreply@laravel-postman.test
MAIL_FROM_NAME="LaravelPostman"

# ============================================
# API SETTINGS
# ============================================
API_DEBUG=false
API_RATE_LIMIT=60
API_TIMEOUT=30
```

### Database Setup

#### Menggunakan MySQL GUI (phpMyAdmin)

1. Buka phpMyAdmin di browser
2. Buat database baru: `laravel_postman`
3. Set charset ke `utf8mb4`
4. Update `.env` dengan credentials Anda

#### Menggunakan Command Line

```bash
# Login ke MySQL
mysql -u root -p

# Di MySQL command line:
CREATE DATABASE laravel_postman CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
EXIT;

# Kembali ke terminal
php artisan migrate --seed
```

### Configuration Files

| File | Purpose |
|------|---------|
| `config/app.php` | App settings & timezone |
| `config/database.php` | Database connections |
| `config/cache.php` | Cache configuration |
| `config/auth.php` | Authentication settings |

---

## 📁 Struktur Folder

```
LaravelPostman/
│
├── 📂 app/
│   ├── Console/                 # Artisan commands
│   ├── Http/
│   │   ├── Controllers/         # Page controllers
│   │   ├── Requests/            # Form validation
│   │   └── Middleware/          # HTTP middleware
│   ├── Models/                  # Eloquent models
│   └── Exceptions/              # Custom exceptions
│
├── 📂 bootstrap/
│   └── app.php                  # App bootstrap
│
├── 📂 config/                   # Configuration files
│   ├── app.php
│   ├── database.php
│   ├── cache.php
│   └── auth.php
│
├── 📂 database/
│   ├── migrations/              # Schema migrations
│   ├── seeders/                 # Database seeders
│   └── factories/               # Model factories
│
├── 📂 public/                   # Web root (accessible publicly)
│   ├── index.php               # Entry point
│   ├── css/                    # Compiled CSS
│   ├── js/                     # Compiled JavaScript
│   └── images/                 # Static images
│
├── 📂 resources/
│   ├── views/                  # Blade templates
│   │   ├── layouts/
│   │   ├── auth/
│   │   ├── dashboard/
│   │   └── api/
│   ├── js/                     # Source JavaScript
│   │   ├── app.js
│   │   └── bootstrap.js
│   └── css/                    # Source CSS
│       └── app.css
│
├── 📂 routes/
│   ├── web.php                 # Web routes
│   ├── api.php                 # API routes
│   ├── auth.php                # Auth routes
│   └── console.php             # Console routes
│
├── 📂 storage/                 # Runtime storage
│   ├── app/                    # Application files
│   ├── logs/                   # Log files
│   └── framework/              # Framework files
│
├── 📂 tests/
│   ├── Feature/                # Feature tests
│   └── Unit/                   # Unit tests
│
├── 📂 node_modules/            # JS dependencies (gitignored)
│
├── .env                        # Environment variables (local)
├── .env.example               # Environment template
├── .gitignore                 # Git ignore rules
├── .editorconfig              # Editor config
├── composer.json              # PHP dependencies
├── composer.lock              # Locked PHP versions
├── package.json               # JS dependencies
├── package-lock.json          # Locked JS versions
├── phpunit.xml                # PHPUnit configuration
├── vite.config.js             # Vite configuration
├── artisan                    # Laravel CLI
├── README.md                  # This file
└── LICENSE                    # MIT License
```

---

## 💻 Panduan Penggunaan

### Development Server

#### Terminal 1: PHP Server
```bash
php artisan serve
# Server berjalan di http://localhost:8000
```

#### Terminal 2: Vite Dev Server
```bash
npm run dev
# Hot reload untuk CSS dan JS
```

### Build untuk Production

```bash
# Optimize & build assets
npm run build

# Clear cache
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

### Artisan Commands Penting

```bash
# ============================================
# MODEL, MIGRATION & SEEDER
# ============================================

# Create model dengan migration dan controller
php artisan make:model Post -m -c

# Create hanya migration
php artisan make:migration create_posts_table

# Create model
php artisan make:model Post

# Create seeder
php artisan make:seeder PostSeeder


# ============================================
# MIGRATION
# ============================================

# Run all pending migrations
php artisan migrate

# Rollback last migration
php artisan migrate:rollback

# Rollback all migrations
php artisan migrate:reset

# Reset and re-run all migrations
php artisan migrate:refresh

# Refresh dan seed
php artisan migrate:refresh --seed


# ============================================
# CACHE & OPTIMIZATION
# ============================================

# Cache configuration
php artisan config:cache

# Cache routes
php artisan route:cache

# Cache views
php artisan view:cache

# Clear all cache
php artisan cache:clear

# Optimize application
php artisan optimize


# ============================================
# MAINTENANCE
# ============================================

# Put app in maintenance mode
php artisan down

# Bring app back up
php artisan up

# Create new user
php artisan tinker
```

### Using Tinker (Interactive Shell)

```bash
php artisan tinker

# Create a user
$user = User::create([
    'name' => 'John Doe',
    'email' => 'john@example.com',
    'password' => bcrypt('password')
]);

# Query users
User::all();

# Exit
exit
```

---

## 📚 API Documentation

### Base URL
```
http://localhost:8000/api
```

### Authentication
Semua API requests memerlukan token Bearer:
```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

### Endpoints

#### 1. User Management

```
GET    /api/users              # List all users
POST   /api/users              # Create new user
GET    /api/users/{id}         # Get user by ID
PUT    /api/users/{id}         # Update user
DELETE /api/users/{id}         # Delete user
```

#### 2. Postman Collections

```
GET    /api/collections           # List collections
POST   /api/collections           # Create collection
GET    /api/collections/{id}      # Get collection detail
PUT    /api/collections/{id}      # Update collection
DELETE /api/collections/{id}      # Delete collection
```

#### 3. API Requests

```
GET    /api/requests             # List requests
POST   /api/requests             # Create request
GET    /api/requests/{id}        # Get request detail
PUT    /api/requests/{id}        # Update request
DELETE /api/requests/{id}        # Delete request
POST   /api/requests/{id}/send   # Send/Execute request
```

#### 4. Analytics

```
GET    /api/analytics/summary     # Analytics summary
GET    /api/analytics/requests    # Request history
```

---

## 🗄️ Database Schema

### Users Table
```sql
CREATE TABLE users (
    id BIGINT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role ENUM('user', 'admin') DEFAULT 'user',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

### Postman Collections Table
```sql
CREATE TABLE collections (
    id BIGINT PRIMARY KEY AUTO_INCREMENT,
    user_id BIGINT NOT NULL,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

### API Requests Table
```sql
CREATE TABLE requests (
    id BIGINT PRIMARY KEY AUTO_INCREMENT,
    collection_id BIGINT NOT NULL,
    name VARCHAR(255) NOT NULL,
    method ENUM('GET', 'POST', 'PUT', 'DELETE', 'PATCH') NOT NULL,
    url TEXT NOT NULL,
    headers JSON,
    body JSON,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP,
    FOREIGN KEY (collection_id) REFERENCES collections(id) ON DELETE CASCADE
);
```

---

## 🧪 Testing

### Menjalankan Tests

```bash
# Run all tests
php artisan test

# Run specific test file
php artisan test tests/Feature/UserTest.php

# Run with coverage report
php artisan test --coverage

# Run unit tests only
php artisan test --testsuite=Unit

# Run feature tests only
php artisan test --testsuite=Feature
```

### Test Structure

```
tests/
├── Feature/
│   ├── UserTest.php
│   ├── CollectionTest.php
│   └── RequestTest.php
└── Unit/
    ├── UserModelTest.php
    └── ValidationTest.php
```

### Example Test

```php
<?php

namespace Tests\Feature;

use Tests\TestCase;
use App\Models\User;

class UserTest extends TestCase
{
    public function test_user_can_register()
    {
        $response = $this->post('/register', [
            'name' => 'John Doe',
            'email' => 'john@example.com',
            'password' => 'password123',
            'password_confirmation' => 'password123',
        ]);

        $response->assertRedirect('/dashboard');
        $this->assertDatabaseHas('users', [
            'email' => 'john@example.com'
        ]);
    }
}
```

---

## 🔧 Troubleshooting

### Error: "No application encryption key has been specified"

```bash
php artisan key:generate
```

### Error: "Access denied for user 'root'@'localhost'"

Periksa konfigurasi database di `.env`:
```bash
DB_HOST=127.0.0.1
DB_USERNAME=root
DB_PASSWORD=your_password
```

### Error: "Database 'laravel_postman' doesn't exist"

```bash
# Create database
mysql -u root -p -e "CREATE DATABASE laravel_postman;"

# Run migrations
php artisan migrate
```

### Error: "SQLSTATE[HY000]: General error: 3065 Expression"

Update `AppServiceProvider.php`:

```php
use Illuminate\Support\ServiceProvider;
use Illuminate\Database\Schema\Builder;

class AppServiceProvider extends ServiceProvider
{
    public function boot()
    {
        Builder::defaultStringLength(191);
    }
}
```

### Composer Error: "No matching version found"

```bash
# Clear composer cache
composer clear-cache

# Update dependencies
composer update
```

### npm Error: "EACCES permission denied"

```bash
# Use sudo untuk Linux/Mac
sudo npm install

# Atau fix npm permissions
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
export PATH=~/.npm-global/bin:$PATH
```

### Clear Cache & Rebuild

```bash
# Artisan cache clear
php artisan cache:clear
php artisan config:clear
php artisan route:clear
php artisan view:clear

# Remove node modules dan rebuild
rm -rf node_modules package-lock.json
npm install
npm run build
```

---

## 🚀 Deployment

### Preparation

```bash
# Install dependencies
composer install --optimize-autoloader --no-dev
npm install
npm run build

# Generate key
php artisan key:generate

# Cache config
php artisan config:cache
php artisan route:cache
```

### Server Requirements

- PHP 8.0+
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- Ctype PHP Extension
- JSON PHP Extension
- BCMath PHP Extension

### Using Shared Hosting

1. Upload files via FTP
2. Set `.env` configuration
3. Run migrations via SSH:
   ```bash
   php artisan migrate
   ```
4. Set file permissions:
   ```bash
   chmod -R 755 storage bootstrap/cache
   ```

### Using Docker

Create `Dockerfile`:

```dockerfile
FROM php:8.0-fpm

RUN apt-get update && apt-get install -y mysql-client

WORKDIR /app

COPY . .

RUN composer install

CMD ["php-fpm"]
```

Run with Docker Compose:

```bash
docker-compose up -d
```

### Using Heroku

1. Create `Procfile`:
   ```
   web: vendor/bin/heroku-php-apache2 public/
   ```

2. Create `app.json` untuk environment variables

3. Deploy:
   ```bash
   git push heroku main
   heroku run php artisan migrate
   ```

---

## 🤝 Kontribusi

Kami menerima kontribusi dari siapa saja! Berikut cara berkontribusi:

### 1. Fork Repository

Klik tombol "Fork" di GitHub

### 2. Clone Fork Anda

```bash
git clone https://github.com/YOUR_USERNAME/LaravelPostman.git
cd LaravelPostman
```

### 3. Buat Branch Fitur

```bash
git checkout -b feature/AmazingFeature
# atau untuk bug fix
git checkout -b fix/BugName
```

### 4. Commit Perubahan

```bash
git add .
git commit -m "Add amazing feature"
# Gunakan conventional commits:
# feat: add new feature
# fix: fix a bug
# docs: documentation changes
# style: code style changes
# refactor: code refactoring
```

### 5. Push ke Branch

```bash
git push origin feature/AmazingFeature
```

### 6. Buat Pull Request

1. Buka GitHub repository
2. Klik "Compare & pull request"
3. Isi deskripsi PR
4. Submit PR

### Coding Standards

- Follow PSR-12 untuk PHP
- Use ES6+ syntax untuk JavaScript
- Tambahkan unit tests untuk feature baru
- Update dokumentasi jika diperlukan
- Minimum 80% test coverage

### Development Workflow

```bash
# 1. Setup development environment
composer install
npm install

# 2. Create feature branch
git checkout -b feature/your-feature

# 3. Make changes and test
npm run dev
php artisan test

# 4. Build for testing
npm run build

# 5. Commit and push
git add .
git commit -m "feat: add your feature"
git push origin feature/your-feature
```

---

## 📞 Support

### Mendapat Bantuan

- 📖 **Documentation**: [Laravel Docs](https://laravel.com/docs)
- 🐛 **Report Bug**: [GitHub Issues](https://github.com/ShiniGOD/LaravelPostman/issues)
- 💬 **Discussion**: [GitHub Discussions](https://github.com/ShiniGOD/LaravelPostman/discussions)
- 📧 **Email**: [eldokusuma3@gmail.com]

### Resources

| Resource | Link |
|----------|------|
| Laravel Documentation | https://laravel.com/docs |
| Laravel Blade | https://laravel.com/docs/blade |
| Eloquent ORM | https://laravel.com/docs/eloquent |
| Laravel Testing | https://laravel.com/docs/testing |
| Vite Documentation | https://vitejs.dev |
| Postman API | https://www.postman.com/api-documentation/ |

---

## 📄 Lisensi

Proyek ini dilisensikan di bawah **MIT License**. Lihat file [LICENSE](LICENSE) untuk detail lengkap.

```
MIT License

Copyright (c) 2024 ShiniGOD

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👨‍💻 Author

**ShiniGOD**
- GitHub: [@ShiniGOD](https://github.com/ShiniGOD)
- Project: [LaravelPostman](https://github.com/ShiniGOD/LaravelPostman)

---

## 🙏 Acknowledgments

- [Laravel Framework](https://laravel.com) - The web framework
- [Postman](https://www.postman.com) - API testing platform
- [Vite](https://vitejs.dev) - Build tool
- Semua contributors dan supporters

---

**Last Updated**: 2024  
**Status**: 🔄 In Development  
**Version**: 1.0.0

---

<div align="center">

Made by ShiniGOD

⭐ Don't forget to star this repo if you find it helpful!

</div>
