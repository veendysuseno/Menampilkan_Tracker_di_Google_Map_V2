# Proyek GPS dan SIM800L dengan Arduino

Proyek ini menggunakan modul GPS dan modul GSM SIM800L untuk mendapatkan data lokasi dan mengirimkannya melalui SMS ke nomor telepon tertentu.

## Deskripsi

Kode ini dirancang untuk membaca data lokasi (latitude dan longitude) dari modul GPS dan kemudian mengirimkan data tersebut dalam bentuk tautan Google Maps melalui SMS menggunakan modul SIM800L.

## Fitur Utama

- **Modul GPS**: Mengambil data lokasi secara real-time (latitude dan longitude).
- **Modul GSM SIM800L**: Mengirimkan data lokasi yang diperoleh dalam bentuk tautan Google Maps ke nomor telepon yang telah ditentukan melalui SMS.

## Komponen yang Dibutuhkan

- Arduino (Uno, Mega, atau model lain yang kompatibel)
- Modul GPS (misalnya, Neo-6M)
- Modul GSM SIM800L
- Kabel jumper

## Cara Kerja

1. **Inisialisasi**:
    - Modul SIM800L dan Serial Monitor diinisialisasi pada kecepatan baud 9600.
    - Modul SIM800L diatur dalam mode pesan teks (AT+CMGF=1).

2. **Looping Utama**:
    - Program akan memeriksa apakah ada data yang masuk dari modul SIM800L.
    - Jika ada data yang masuk, program akan memeriksa apakah ada perintah "ON" yang diterima melalui SMS.
    - Jika perintah "ON" diterima, program akan mengirimkan pesan SMS yang berisi tautan Google Maps dengan lokasi saat ini.

3. **Fungsi GPS**:
    - Fungsi ini digunakan untuk membaca data GPS dari Serial dan mengonversinya menjadi latitude dan longitude.
    - Tautan Google Maps dibuat berdasarkan data latitude dan longitude yang diperoleh.

## Cara Menggunakan

1. Hubungkan modul GPS dan SIM800L ke Arduino sesuai dengan pengaturan pin yang ditentukan di dalam kode.
2. Unggah kode ini ke Arduino.
3. Kirim SMS dengan format yang sesuai ke modul SIM800L yang terhubung dengan Arduino.
4. Modul akan mengirimkan tautan lokasi Google Maps ke nomor yang ditentukan jika perintah yang diterima adalah "ON".

## Contoh SMS

- Untuk mengaktifkan pengiriman lokasi, kirim SMS dengan isi "ON" ke nomor yang terhubung dengan SIM800L.

## Catatan

- Pastikan nomor telepon yang dimasukkan dalam kode sudah benar.
- Modul GPS memerlukan waktu beberapa detik hingga menit untuk mengunci sinyal satelit dan memberikan data lokasi yang akurat.
