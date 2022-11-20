# Form

Seprti di django admin yang menyediakan form secara otomatis, kita bisa membuat form yang identik dengan model menggunakan `modelform`. Pertama buat berkas di `guestbook` dengan nama `forms.py` lalu isikan seperti berikut

```python
from django.forms import ModelForm

from guestbook.models import GuestBook


class GuestBookForm(ModelForm):
    class Meta:
        model = GuestBook
        exclude = ["date_created", "date_updated"]

```

Di `views` yang sudah dibuat ubah menjadi

```python
from django.shortcuts import render

from guestbook.forms import GuestBookForm


# Create your views here.
def guest_form(request):
    if request.method == "POST":
        pass
    else:
        form = GuestBookForm()
    return render(request, "layout.html", context={"form": form})

```
Lalu di template
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
    <form action="/guest-book/" method="POST">
        {% csrf_token %}
         {{ form.as_p }}
        <input type="submit" value="Save">
    </form>
</body>
</html>
```

Hasilnya

<img src="assets/views-4.png" load="lazy">

## Handle Post
Ubah bagian views menjadi seperti berikut
```python
from django.shortcuts import redirect, render

from guestbook.forms import GuestBookForm


# Create your views here.
def guest_form(request):
    if request.method == "POST":
        form = GuestBookForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect("/guest-book/")
    else:
        form = GuestBookForm()
    return render(request, "layout.html", context={"form": form})
```

Validasi juga sudah terbawa


<img src="assets/views-5.png" load="lazy">

Dan jika sukses data akan masuk


<img src="assets/views-6.png" load="lazy">