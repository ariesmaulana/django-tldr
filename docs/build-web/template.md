# Template

Di django template berfungsi untuk hal yang berkaitan dengan user interface atau yang akan dimunculkan di browser.

## Konfigurasi

Buat satu folder di `guestbook` dengan nama `templates` dan isikan berkas dengan nama `layout.html` atau nama yang kamu inginkan, dan isikan kode html seperti berikut

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    halo From template
</body>
</html>
```

Ubah fungsi di views menjadi
```python
from django.shortcuts import render


# Create your views here.
def guest_form(request):
    return render(request, "layout.html")
```

Dan saat kunjungi lagi hasilnya


<img src="assets/views-2.png" load="lazy">

## Passing param

Untuk mngirimkan variable dari views bisa menggunakan `context` di dalam function views

```python
from django.shortcuts import render


# Create your views here.
def guest_form(request):
    label = "Greeting from views"
    return render(request, "layout.html", context={"label": label})
```

lalu di template

```html
<body>
    {{ label }}
</body>
```

Hasilnya

<img src="assets/views-3.png" load="lazy">