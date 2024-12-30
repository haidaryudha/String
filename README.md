# String
### Penjelasan Lengkap Kode Validasi Formulir

### 1. Import Modul

```python
import re
```

Kode ini mengimpor modul **`re`** yang digunakan untuk bekerja dengan **regular expression** (ekspresi reguler). Regular expression sering digunakan untuk mencocokkan pola tertentu dalam string. Namun, dalam kode ini, modul tersebut tidak digunakan sama sekali. Oleh karena itu, baris ini sebenarnya bisa dihapus tanpa memengaruhi program.

---

### 2. Definisi Fungsi Validasi

```python
def validasi_form(nama, nomor_telepon, email):
```

Baris ini mendefinisikan sebuah fungsi bernama **`validasi_form`** yang menerima tiga parameter, yaitu:

1. **`nama`** – Mewakili input nama lengkap yang diberikan oleh pengguna.
2. **`nomor_telepon`** – Mewakili input nomor telepon dari pengguna.
3. **`email`** – Mewakili input alamat email dari pengguna.

Fungsi ini digunakan untuk melakukan serangkaian pemeriksaan (validasi) terhadap data yang dimasukkan oleh pengguna.

---

### 3. Inisialisasi List untuk Menyimpan Error

```python
errors = []
```

Baris ini mendeklarasikan sebuah list kosong bernama **`errors`**. List ini akan digunakan untuk menyimpan pesan-pesan kesalahan yang muncul selama proses validasi. Jika tidak ada kesalahan, list ini akan tetap kosong hingga akhir proses.

---

### 4. Validasi Nama Lengkap

```python
if not nama.isalpha():
    errors.append("Nama lengkap harus hanya berisi huruf.")
```

Bagian ini bertujuan untuk memeriksa apakah input **`nama`** hanya terdiri dari huruf (tanpa angka, simbol, atau spasi).

- Fungsi **`isalpha()`** mengembalikan nilai **`True`** jika semua karakter dalam string adalah huruf alfabet, dan **`False`** jika ada karakter selain huruf.
- **`not nama.isalpha()`** akan menghasilkan **`True`** jika terdapat karakter yang bukan huruf dalam input.
- Jika kondisi tersebut terpenuhi, pesan kesalahan *"Nama lengkap harus hanya berisi huruf."* akan ditambahkan ke dalam list **`errors`**.

**Contoh:**

- Input: **"John123"** → Pesan error ditambahkan.
- Input: **"John"** → Valid, tidak ada pesan error.

---

### 5. Validasi Nomor Telepon

```python
if not nomor_telepon.isdigit():
    errors.append("Nomor telepon harus hanya berisi angka.")
```

Kode ini memeriksa apakah input **`nomor_telepon`** hanya terdiri dari angka.

- Fungsi **`isdigit()`** mengembalikan **`True`** jika semua karakter dalam string adalah angka (0-9), dan **`False`** jika mengandung karakter selain angka.
- **`not nomor_telepon.isdigit()`** akan bernilai **`True`** jika ada karakter non-angka di dalam input.
- Jika input tidak valid, pesan error ditambahkan ke list **`errors`**.

**Contoh:**

- Input: **"123456"** → Valid, tidak ada error.
- Input: **"123-456"** → Tidak valid, pesan error ditambahkan.

---

### 6. Validasi Email

```python
if "@" not in email or "." not in email:
    errors.append("Email harus mengandung karakter '@' dan '.'.")
```

Bagian ini memeriksa apakah email yang dimasukkan memiliki karakter **`@`** dan **`.`** (titik). Kedua karakter ini dianggap sebagai elemen dasar yang harus ada dalam format email yang valid.

- Pernyataan **`"@" not in email`** mengecek apakah karakter **`@`** ada di dalam email.
- Pernyataan **`"." not in email`** mengecek apakah karakter **`.`** ada di dalam email.
- Jika salah satu dari kedua kondisi tersebut **`True`**, pesan error ditambahkan.

**Contoh:**

- Input: **"********[user@gmail.com](mailto\:user@gmail.com)********"** → Valid, tidak ada error.
- Input: **"usergmail.com"** → Tidak valid, pesan error ditambahkan.
- Input: **"user\@gmailcom"** → Tidak valid, pesan error ditambahkan.

> **Catatan:** Validasi ini sangat sederhana dan tidak cukup kuat untuk menangkap format email yang lebih kompleks. Untuk validasi email yang lebih akurat, sebaiknya gunakan **regular expression**.

---

### 7. Menampilkan Hasil Validasi

```python
if errors:
    for error in errors:
        print(error)
else:
    print("Data pendaftaran valid.")
```

Setelah semua validasi dilakukan:

- Jika list **`errors`** tidak kosong (berisi pesan kesalahan), maka setiap pesan akan dicetak satu per satu menggunakan loop **`for`**.
- Jika list **`errors`** kosong, artinya semua input valid, dan program akan mencetak pesan: *"Data pendaftaran valid."*

---

### 8. Input Data dari Pengguna

```python
nama = input("Masukkan nama lengkap: ")
nomor_telepon = input("Masukkan nomor telepon: ")
email = input("Masukkan email: ")
```

Kode ini meminta pengguna untuk memasukkan data mereka secara interaktif melalui terminal atau konsol:

1. Nama lengkap.
2. Nomor telepon.
3. Email.

Data yang dimasukkan kemudian disimpan dalam variabel masing-masing, yang akan digunakan untuk proses validasi selanjutnya.

---

### 9. Memanggil Fungsi Validasi

```python
validasi_form(nama, nomor_telepon, email)
```

Baris ini memanggil fungsi **`validasi_form`** dengan parameter input yang diambil dari pengguna. Fungsi ini akan menjalankan semua pemeriksaan validasi dan menampilkan hasilnya di layar.

---
![Screenshot 2024-12-30 221027](https://github.com/user-attachments/assets/eb218435-3cc4-4127-ba98-1356af247d30)

