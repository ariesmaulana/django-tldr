# Admin & Form

## Admin
Django sudah menyediakan dashboard admin secara `default` untuk mempercepat proses development, namun sebelum mengakses django admin kita harus membuat superuser dahulu, untuk membuatnya jalankan perintah berikut:

```bash
python manage.py createsuperuser 
Username (leave blank to use 'username'): admin <--input username yang diinginkan
Email address: admin@admin.com <--input email yang diinginkan
Password: <--input password yang diinginkan
Password (again): <-- ulangi password
Superuser created successfully.
```

Setelah selesai, bisa kunjungi `localhost:8000/admin` dan masukan username dan password yang tadi dibuat

<img src="assets/admin-1.png" loading="lazy" >

Halaman awal django admin

<img src="assets/admin-2.png" loading="lazy" >

## Mendaftarkan App di Admin

Untuk mendaftarkan app di menu admin, cukup buka `guestbook/admin.py` dan tambahkan sebagai berikut
```python
from django.contrib import admin

from guestbook.models import GuestBook

# Register your models here.


@admin.register(GuestBook)
class GuestBookAdmin(admin.ModelAdmin):
    pass

```

Hasilnya app yang dibuat sudah terdaftar menunya

<img src="assets/admin-3.png" loading="lazy" >

Juga sudah tersedia form nya secara langsung

<img src="assets/admin-4.png" loading="lazy" >

Serta tabel

<img src="assets/admin-5.png" loading="lazy" >