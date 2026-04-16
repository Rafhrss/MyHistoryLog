## Sebelum Menggunakan Neon
```bash
django
mysqlclient
pymysql
```

## Konfigurasi Menggunakan Neon
Semua kondigurasi ini ada di docs neon.com
```bash
pip install "psycopg[binary]" python-dotenv

# Add these at the top of your settings.py || AMbil sisanya di docs saja
from os import getenv
from dotenv import load_dotenv
load_dotenv()
Biarkan Connection Pooling aktif agar setiap user buka database selalu aktif dan tidak buka tutup traffic terus

python manage.py migrate                        = migrate models agar masuk ke neon
python manage.py flush                          = bersihkan semua data cache di model
python manage.py dumpdata --natural-foreign --natural-primary -e contenttypes -e auth.Permission --indent 2 > dataku_clean.json         = ubah database mysql menjadi Postgresql dalam bentuk JSON dulu "ubah database ke XAMPP dulu"
python manage.py loaddata dataku_clean.json     = ubah UTF-16 => UTF-8

```