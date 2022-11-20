# Setup

Di sini kita akan membuat aplikasi buku tamu menggunakan Django. 

# Install Django

Untuk memasang django yang kita perlukan hanyalah pip:
```bash
pip install Django
```

Buat folder kosong yang akan menjadi projek django

```bash
mkdir project-django && cd project-django
```

Gunakan perintah cli django untuk membuat projek

```bash
django-admin startproject core .
```

Lalu jalankan django dengan perintah

```bash
python manage.py runserver
```

Saat pertama kali menjalankan django akan mendapatkan warning seperti ini
```bash
You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
```
Jangan khawatir itu hanya info agar django bisa berjalan dengan baik dari awal maka perlu memasang konfigurasi dasar, cukup jalankan perintah

```bash
python manage.py migrate
```

> Dokumentasi membuat django app: <a href="https://docs.djangoproject.com/en/3.2/intro/tutorial01/" target="_blank">Starting django app</a>
