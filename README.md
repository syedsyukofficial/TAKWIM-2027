# Takwim 2027 Malaysia · 1448–1449H

Takwim interaktif dalam satu fail (`index.html`):

- Cuti umum 2027 untuk 16 negeri dan wilayah, mengikut Jadual Hari Kelepasan Am JPM
- Cuti sekolah 2027 (KPM Kumpulan A dan B)
- Tarikh Hijri setiap hari, dikira dengan kriteria MABIMS dan sepadan dengan senarai JAKIM
- Hujung minggu ikut negeri (Kedah, Kelantan dan Terengganu: Jumaat–Sabtu)
- Acara peribadi dengan kotak berwarna
- Eksport ke Google Calendar
- Cetak PDF A4
- Paparan **Hari Ini**: tarikh hari ini (Masihi, Hijri dan tulisan Arab) dan senarai tarikh akan datang
- Boleh dipasang di telefon sebagai aplikasi (PWA), dan boleh dibuka tanpa internet

## Di mana acara peribadi disimpan?

| Keadaan | Tempat simpan | Siapa boleh nampak |
|---|---|---|
| Tidak log masuk | Pelayar (browser) peranti itu sahaja | Pengguna peranti itu sahaja |
| Log masuk dengan Google | Google Drive pengguna sendiri, dalam folder data aplikasi yang tersembunyi | Pengguna itu sahaja. Acara ikut dia di semua peranti. |

Tiada pelayan dan tiada pangkalan data pusat. Pemilik laman web juga tidak dapat melihat acara pengguna.

---

## 1. Terbitkan di GitHub Pages

1. Log masuk ke GitHub, kemudian tekan **New repository**. Contoh nama: `takwim-2027`. Pilih **Public**.
2. Tekan **Add file → Upload files**. Ekstrak fail zip dahulu, kemudian seret **semua** kandungannya ke halaman upload:
   ```
   index.html
   manifest.webmanifest
   sw.js
   README.md
   icons/   (seret folder ini sekali)
   ```
   Tekan **Commit changes**.
3. Pergi ke **Settings → Pages**. Di bawah *Branch*, pilih `main` dan folder `/ (root)`, kemudian tekan **Save**.
4. Selepas 1–2 minit, laman siap di:
   `https://NAMA-PENGGUNA.github.io/takwim-2027/`

Pada tahap ini takwim sudah boleh digunakan. Acara disimpan dalam pelayar setiap pengguna.

---

## 2. Pasang di telefon sebagai aplikasi

**Android (Chrome):**
1. Buka `https://NAMA-PENGGUNA.github.io/takwim-2027/` dalam Chrome.
2. Tekan butang **⤓ Pasang aplikasi** di bahagian atas laman, atau menu **⋮ → Add to Home screen / Install app**.
3. Ikon **Takwim 2027** akan muncul di skrin utama. Bila dibuka, ia terus memaparkan **Hari Ini**, tanpa bar alamat.

**iPhone (Safari):** tekan butang **Kongsi**, kemudian pilih **Add to Home Screen**.

Selepas dibuka sekali dengan internet, aplikasi boleh dibuka tanpa internet.

**Bila mengemas kini `index.html`:** buka `sw.js` dan tukar nombor dalam `const VERSION = 'takwim2027-v3';` kepada `v4`, `v5` dan seterusnya. Dengan cara itu, telefon pengguna akan mengambil versi baharu.

---

## 3. (Pilihan) Aktifkan "Log masuk dengan Google"

Langkah ini membolehkan acara disimpan dalam akaun Google setiap pengguna, supaya ia sama di telefon dan komputer. Ia percuma dan dibuat sekali sahaja.

1. Buka <https://console.cloud.google.com/> dan log masuk dengan Gmail anda.
2. Pada bahagian atas, tekan **Select a project → New project**. Contoh nama: `Takwim 2027`. Tekan **Create**.
3. Pergi ke **APIs & Services → Library**, cari **Google Drive API**, kemudian tekan **Enable**.
4. Pergi ke **APIs & Services → OAuth consent screen** (atau **Google Auth Platform → Branding**):
   - User type: **External**
   - App name: `Takwim 2027`, kemudian isi email sokongan anda
   - Di bahagian **Audience → Test users**, tambah Gmail ahli keluarga yang akan guna (maksimum 100 orang).
     Jika mahu terbuka kepada sesiapa sahaja, tekan **Publish app**.
5. Pergi ke **APIs & Services → Credentials → Create credentials → OAuth client ID**:
   - Application type: **Web application**
   - **Authorized JavaScript origins:** `https://NAMA-PENGGUNA.github.io`
   - Tekan **Create**, kemudian salin **Client ID** (berakhir dengan `.apps.googleusercontent.com`).
6. Di GitHub, buka `index.html` dan tekan ikon pensel (Edit). Cari baris ini:

   ```js
   const GOOGLE_CLIENT_ID = '';
   ```

   Tampal Client ID di antara tanda petik:

   ```js
   const GOOGLE_CLIENT_ID = '1234567890-abc...apps.googleusercontent.com';
   ```

   Tekan **Commit changes**.
7. Muat semula laman. Butang **Log masuk dengan Google** akan muncul dalam panel *Simpan & kongsi*.

**Kebenaran yang diminta:** `drive.appdata` sahaja. Aplikasi hanya boleh membaca dan menulis fail datanya sendiri (`takwim-2027.json`) dalam folder tersembunyi. Ia **tidak boleh** melihat fail lain dalam Google Drive pengguna.

**Nota:** Sebelum aplikasi di-*publish* atau disahkan oleh Google, pengguna akan nampak amaran "Google hasn't verified this app". Tekan **Continue** untuk teruskan. Ini normal untuk aplikasi peribadi atau keluarga.

---

## Sumber data

- Jadual Hari Kelepasan Am Persekutuan & Negeri 2027, Bahagian Kabinet, Perlembagaan dan Perhubungan Antara Kerajaan, JPM
- Tarikh-Tarikh Penting Dalam Islam 2027 / 1448–1449H, JAKIM
- Kalendar Akademik Tahun 2027, KPM

Aidilfitri, Aidiladha dan Deepavali tertakluk kepada perubahan. 1 Ramadan, 1 Syawal dan 10 Zulhijjah tertakluk kepada pengisytiharan Penyimpan Mohor Besar Raja-Raja. Cuti ganti tertakluk kepada pengumuman rasmi kerajaan negeri.
