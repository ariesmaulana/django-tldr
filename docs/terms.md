Django bisa dibilang sebagai fullstack web framework seperti Rails atau Laravel, namun dalam django ada beberapa istilah yang mungkin sama dan sedikit berbeda dengan framework sejenis, berikut adalah beberapa istilah yang cukup sering muncul.

## Projek
Django projek adalah keseluruhan aplikasi yang dibuat, saat pertama kali install, django sudah memasang konfigurasi dasar.

Struktur dasar projek django
```
├── <projek-name>
│   ├── asgi.py
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py

```
> dokumentasi resmi: <a href="https://docs.djangoproject.com/en/3.2/glossary/#term-project" target="_blank">Project</a>

## APP
Django APP adalah "module" di dalam projek django, bisa sebagai "module" yang berdiri sendiri ataupun "module" yang saling terkait.
Struktur projek django yang sudah terpasang sebuah app bernama blog
```
.
├── blog
│   ├── admin.py
│   ├── apps.py
│   ├── __init__.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── <projek-name>
│   ├── asgi.py
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py


```

## Model
Mirip dengan beberapa framework lainnya, Model di django bertindak sebagai layer dari framework ke database, salah satu fitur yang powerfull di django model adalah: model yang kita buat adalah representasi dari table yang akan kita gunakan.

## View
Sedikit berbeda dengan framework MVC pada umumnya, pada framework lain View berfungsi sebagai penanggung jawab UI sedangkan untuk logika pemograman dipasang di Controller. Di django View ini bertindak sebagai "controller"

## Template
Fitur yang bertanggung jawab untuk UI yang akan diperlihatkan kepada user.

## Form
Sesuai namanya, fitur ini bertanggung jawab dalam membuat form yang nantiya akan membentuk kumpulan field-field yang dibutuhkan, misalnya dapam operasi CRUD.

> dokumentasi resmi: <a href="https://docs.djangoproject.com/en/3.2/ref/applications/" target="_blank">App</a>

> dokumentasi resmi terkait: <a href="https://docs.djangoproject.com/en/3.2/glossary/" target="_blank">Istilah umum di django</a>
