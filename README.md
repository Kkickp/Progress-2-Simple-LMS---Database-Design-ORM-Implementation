# Simple LMS – Docker & Django Foundation

# 🐳 Docker Services

Project ini menggunakan **Docker Compose** dengan 2 service utama.

## 1️⃣ Web Service (Django)

Image dibangun dari Dockerfile.

Port:

```
8000:8000
```

Service ini menjalankan:

```
python manage.py runserver 0.0.0.0:8000
```

---

## 2️⃣ Database Service (PostgreSQL)

Image:

```
postgres:15
```

Environment variables:

```
POSTGRES_DB=lms_db
POSTGRES_USER=lms_user
POSTGRES_PASSWORD=lms_password
```

Database data disimpan menggunakan **Docker volume**.

---

# ⚙️ Environment Variables

File `.env` digunakan untuk menyimpan konfigurasi database.

Contoh `.env.example`:

```
DEBUG=True

POSTGRES_DB=lms_db
POSTGRES_USER=lms_user
POSTGRES_PASSWORD=lms_password
POSTGRES_HOST=db
POSTGRES_PORT=5432
```

Copy file ini menjadi `.env` sebelum menjalankan project.

---

# 🚀 Cara Menjalankan Project

## 1️⃣ Clone Repository

```
git clone https://github.com/Kkickp/Progress-1-Simple-LMS---Docker-Django-Foundation
cd simple-lms
```

---

## 2️⃣ Build Docker Image

```
docker compose build
```

---

## 3️⃣ Jalankan Container

```
docker compose up
```

Docker akan menjalankan:

* Django container
* PostgreSQL container

---

## 4️⃣ Jalankan Migration

Buka terminal baru:

```
docker compose exec web python manage.py migrate
```

---

## 5️⃣ Akses Django

Buka browser:

```
http://localhost:8000
```

Jika berhasil akan muncul halaman:

```
The install worked successfully! Congratulations!
```

---

## Docker Containers Running

```
docker ps
```

Menampilkan container:

```
django_app
postgres_db
```

---

# 🧪 Testing Database Connection

Jalankan migration:

```
docker compose exec web python manage.py migrate
```
