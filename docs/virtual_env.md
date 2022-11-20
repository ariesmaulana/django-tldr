# Virtual env

Salah satu rekomendasi dalam membuat website dengan django adalah menggunakan virtual env (untuk informasi beragam cara membuat `development environmet` bisa mengacu kepada [Development ENV](ekstra/development_env)). 

## Membuat Virtual env

Pertama buat folder yang akan kita gunakan sebagai projek

```bash
mkdir <projek-folder> && cd <projek-folder>
```

Lalu gunakan perintah
```bash
python -m venv venv/
```
Untuk mengunakan virtual env dengan cara
```bash
source venv/bin/activate
```

Untuk memastikan bahwa python yang kita gunakan adalah python versi virtual env, kita bisa cek dengan cara
```bash
 which python
>> /path/projek-folder/venv/bin/python
```

> dokumentasi resmi terkait: <a href="https://docs.python.org/3/library/venv.html" target="_blank">Virtualenv</a>