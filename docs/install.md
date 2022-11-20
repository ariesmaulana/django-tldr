# Install
Saat ini django sudah versi 4 dan versi LTS terakhir yaitu versi 3.2 dan direkomendasikan menggunakan python 3 versi terakhir.Demi kenyamanan bersama saya akan menggunakan referensi dari versi LTS.

Untuk memasang django sama dengan memasang python package yang lain
```bash
pip install Django
```
Untuk memulai membuat project menggunakan perintah
```
django-admin startproject <nama-project>
```
Perintah di atas akan membuat satu folder sesuai dengan nama projek.

Atau jika sudah menyiapkan folder kosong dan ingin memasang projek django di dalamnya bisa menggunakan perintah 
```
django-admin startproject <nama-project> .
```
Lalu di dalam folder projek jalankan django dengan perintah
```
python manage.py runserver
```
Selamat, anda telah berhasil memasang dan menjalankan projek django.

+ Preferensi Pribadi+ +

    Saat membuat projek saya biasa melakukan hal ini
    ```bash
    mkdir my-project && cd my-project
    ```

    Buat projek jango dengan nama *core* atau *config*
    ```bash
    django-admin startproject core .
    ```
    Sehingga hasil akhir akan seperti ini
    ```bash
    .my-project
    ├── core
    │   ├── asgi.py
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── db.sqlite3
    ├── manage.py

    ```


Dokumentasi resmi: https://docs.djangoproject.com/en/3.2/intro/install/