# Laporan Praktikum — Box Model, Flexbox, dan Positioning CSS

- Nama: Suci Salwa Amalia
- Mata Kuliah: Pemrograman Web
- Topik: CSS Box Model, Flexbox, Positioning, dan Tata Letak Responsif

---

## 1. Percobaan 1 — Box Model (`p1_boxmodel.html`)

Pada percobaan pertama, saya menguji perbedaan perhitungan ukuran antara `content-box` dan `border-box`, jarak antar elemen blok (*margin collapsing*), serta perilaku elemen `inline` pada tautan menu.

| Elemen / Bagian | Properti Utama | Hasil Pengamatan di Browser / DevTools |
| :--- | :--- | :--- |
| Kotak A (`content-box`) | `width: 300px`, `padding: 20px`, `border: 5px solid` | Lebar total menjadi `350px` karena padding kiri-kanan (`40px`) dan border kiri-kanan (`10px`) menambah lebar di luar `300px`. |
| Kotak B (`border-box`) | `width: 300px`, `padding: 20px`, `border: 5px solid` | Lebar total tetap `300px` karena padding dan border dihitung di dalam lebar `300px`, sehingga area konten menyesuaikan. |
| Judul & Paragraf | `margin-bottom: 30px` pada judul dan `margin-top: 20px` pada paragraf | Jarak vertikal di antara keduanya tidak menjadi `50px`, melainkan saling tumpang tindih dan mengambil nilai terbesar (`30px`). |
| Tombol Menu (`<a>`) | Bawaan `inline` | Tampil sejajar menyamping, padding atas-bawah tidak mendorong baris teks di atas/bawah secara penuh seperti elemen blok. |

---

## 2. Percobaan 2 — Flexbox Lab (`p2_flexlab.html`)

Awalnya item A, B, dan C menumpuk ke bawah karena elemen `div` bersifat `block`. Setelah container `.lab` diberi `display: flex;`, ketiga item langsung berjajar ke samping dalam satu baris.

- Saat `justify-content` diubah (seperti `center`, `space-between`, atau `space-around`), posisi item pada sumbu utama bergeser sesuai nilai yang dipilih.
- Saat `align-items` diubah (seperti `center`, `flex-start`, atau `flex-end`), perataan item pada sumbu tegak lurus ikut berubah di dalam tinggi wadah `.lab` (`240px`).
- Saat `flex-direction` diubah menjadi `column`, arah susunan kembali menjadi vertikal dari atas ke bawah.

---

## 3. Percobaan 3 — Positioning (`p3_positioning.html`)

Pada percobaan ini saya mencoba beberapa jenis posisi CSS:

- **Header (`.header`)**: Menggunakan `position: sticky; top: 0;` agar tetap terlihat di bagian atas saat halaman digulir ke bawah, tanpa menutupi teks awal pada kondisi normal.
- **Badge notifikasi (`.badge`)**: Menggunakan `position: absolute;` di dalam tombol `.notif` yang berstatus `position: relative;`, sehingga angka `3` menempel di pojok kanan atas ikon lonceng.
- **Tumpukan lapis (`.lapis-1`, `.lapis-2`, `.lapis-3`)**: Diatur menggunakan `position: relative;` pada `.tumpuk` dan `position: absolute;` pada tiap kotak dengan koordinat `left` dan `top` berbeda agar saling menumpuk bertingkat.
- **Tombol Bantuan (`.chat`)**: Menggunakan `position: fixed;` di pojok kanan bawah sehingga posisinya tetap mengikuti layar meskipun halaman di-scroll.

---

## 4. Percobaan 4 — Dashboard SIAKAD Mini (`p4_dasboard.html` & `style.css`)

Pada bagian ini, struktur HTML dipisahkan dari file gaya `style.css` dan dilengkapi beberapa penyesuaian:

1. **Profil di navbar**: Menambahkan inisial avatar (`AP`) dan teks `Admin Prodi` di sisi kanan navbar sejajar dengan tombol notifikasi dan `Logout`.
2. **Menu Pengaturan di bawah sidebar**: Menggunakan `margin-top: auto;` pada `.menu .menu-pengaturan` di tampilan desktop agar posisinya terdorong ke bagian bawah sidebar.
3. **Label "Baru" pada kartu**: Memberi `position: relative;` pada `.kartu-baru` dan `position: absolute;` pada `.label-baru` agar badge kecil menempel di pojok kanan atas kartu **Kelas Hari Ini**.
4. **Tampilan responsif (`<= 768px`)**: Pada layar kecil, susunan `.wrapper` berubah menjadi kolom (`flex-direction: column`), menu sidebar menyesuaikan agar tidak memakan ruang berlebih, dan nama profil disembunyikan agar navbar tetap muat.

### Bukti Tampilan

- **Tampilan Desktop:**

![Tampilan Desktop](desktop.png)

- **Tampilan Mobile:**

![Tampilan Mobile](mobile.png)

---

## 5. Kesimpulan

Dari praktikum ini dapat disimpulkan bahwa pengaturan `box-sizing: border-box` memudahkan perhitungan ukuran elemen agar tidak melebar tak terduga. Flexbox membantu menyusun tata letak satu arah serta membuat halaman lebih mudah disesuaikan di berbagai ukuran layar, sedangkan positioning (`relative`, `absolute`, `sticky`, dan `fixed`) berguna untuk mengatur penempatan elemen tertentu seperti badge, header, dan tombol melayang.