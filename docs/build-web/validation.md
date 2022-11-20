# Validation

Validation adalah hal lumrah dalam operasi crud, validasi berguna untuk menjaga agar data yang disimpan bersih. Sebenarnya django model sudah memiliki default validation yang sudah terpasang, ambil contoh field berikut

```python
identity_number = models.CharField(max_length=100)
```

Satu baris kode di atas sudah mewakili beberapa validasi:

- field tersebut berupa data varchar
- field tersebut maksimal karakter hanya 100
- field tersebut (di database) tidak boleh kosong
- field tersebut (di form) wajib diisi

## Django Validation

Dengan menambahkan validator seperti ini field akan berubah memiliki validasi minimal karakter sebanyak 25
```python
from django.core.validators import MinLengthValidator
from django.db import models


# Create your models here.
class GuestBook(models.Model):

    KTP = 1
    SIM = 2
    DLL = 3
    IDENTITY_CHOICE = (
        (KTP, "KTP"),
        (SIM, "SIM"),
        (DLL, "Dll"),
    )

    name = models.CharField(max_length=100, validators=[MinLengthValidator(25)])
    identity_type = models.PositiveIntegerField(choices=IDENTITY_CHOICE)
    identity_number = models.CharField(max_length=100)
    reason = models.TextField()

    date_created = models.DateTimeField(auto_now_add=True)
    date_updated = models.DateTimeField(auto_now=True)

    def __str__(self):
        return self.name

```
<img src="assets/admin-6.png" loading="lazy" >

# Custom validation

Jika kita punya memiliki aturan sendiri yang tidak ada di django kita bisa buat dengan menambahkan fungsi validator sendiri, membuat validasi untuk nomor identitas tidak boleh memiliki spasi

Buat berkas di `guestbook` dengan nama `validator.py` lalu tambahkan kode berikut

```python
from django.core.exceptions import ValidationError
from django.utils.translation import gettext_lazy as _


def DissalowSpace(value):
    if " " in value:
        raise ValidationError(
            _("%(value)s contain a space!"),
            params={"value": value},
        )
```
Lalu di model tambahkan

```python
from django.core.validators import MinLengthValidator
from django.db import models

from guestbook.validator import DissalowSpace


# Create your models here.
class GuestBook(models.Model):

    KTP = 1
    SIM = 2
    DLL = 3
    IDENTITY_CHOICE = (
        (KTP, "KTP"),
        (SIM, "SIM"),
        (DLL, "Dll"),
    )

    name = models.CharField(max_length=100, validators=[MinLengthValidator(25)])
    identity_type = models.PositiveIntegerField(choices=IDENTITY_CHOICE)
    identity_number = models.CharField(max_length=100, validators=[DissalowSpace])
    reason = models.TextField()

    date_created = models.DateTimeField(auto_now_add=True)
    date_updated = models.DateTimeField(auto_now=True)

    def __str__(self):
        return self.name

```

Hasilnya


<img src="assets/admin-7.png" loading="lazy" >