# View

Di django view merupakan "controller" dalam konsep MVC, ada dua pendektan dalam view di django:
- Class Based Views
- Function Based View

Di bagian ini saya fokus di `function based view`

Buat halaman yang nantinya akan memunculkan form guest book

## Function View

Dalam view tambahkan fungsi berikut

```python
from django.http import HttpResponse
from django.shortcuts import render


# Create your views here.
def guest_form(request):
    return HttpResponse("Hallo")
```

Agar view bisa diakses perlu mendaftarkan fungsi view ke dalam urls, buat berkas `urls.py` di dalam `guestbook`

```python
from django.urls import path

from guestbook.views import guest_form

urlpatterns = [
    path("", guest_form),
]
```

Setelah itu daftarkan `guestbook/urls.py` ke setting `urls.py`
```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("admin/", admin.site.urls),
    path("guest-book/", include("guestbook.urls")),
]

```

Saat akses `localhost:8000/guest-book/` akan muncul

<img src="assets/views-1.png" load="lazy">