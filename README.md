# Jam Digital Arduino dengan LCD 20x4, RTC DS3231, dan Buzzer

Proyek ini adalah implementasi jam digital sederhana menggunakan Arduino Uno, yang menampilkan waktu, tanggal, dan hari pada layar LCD 20x4. Proyek ini juga dilengkapi dengan modul RTC DS3231 untuk menjaga akurasi waktu dan buzzer yang berbunyi setiap detik sebagai indikator.

## Deskripsi

Jam digital ini menampilkan informasi berikut pada LCD:
- Baris 1: Nama hari (dalam bahasa Indonesia)
- Baris 2: Tanggal dalam format DD/MM/YYYY
- Baris 3: Waktu dalam format HH:MM:SS
- Baris 4: Pesan tetap "SMP BQ Islamic BS Bogor"

Buzzer akan berbunyi dengan frekuensi 1000 Hz selama 50 ms setiap detik untuk memberikan indikasi waktu.

## Fitur

- **Tampilan Waktu Real-Time**: Menggunakan RTC DS3231 untuk akurasi tinggi.
- **Tampilan LCD 20x4**: Menampilkan informasi waktu dan tanggal dengan jelas.
- **Buzzer Indikator**: Bunyi setiap detik untuk konfirmasi waktu.
- **Bahasa Indonesia**: Nama hari ditampilkan dalam bahasa Indonesia.
- **Simulasi Wokwi**: Dapat disimulasikan di platform Wokwi.

## Komponen yang Dibutuhkan

- Arduino Uno
- LCD 20x4 (dengan interface paralel)
- Modul RTC DS3231
- Buzzer pasif
- Kabel jumper
- Breadboard (opsional)

## Wiring Diagram

Berikut adalah koneksi komponen berdasarkan diagram Wokwi:

- **LCD 20x4**:
  - RS → Pin 7 Arduino
  - E → Pin 6 Arduino
  - D4 → Pin 5 Arduino
  - D5 → Pin 4 Arduino
  - D6 → Pin 3 Arduino
  - D7 → Pin 2 Arduino
  - VSS → GND
  - VDD → 5V
  - V0 → Potensiometer (untuk kontras)
  - A → 5V (backlight)
  - K → GND (backlight)

- **RTC DS3231**:
  - VCC → 5V Arduino
  - GND → GND Arduino
  - SDA → A4 Arduino
  - SCL → A5 Arduino

- **Buzzer**:
  - Pin positif → Pin 8 Arduino
  - Pin negatif → GND Arduino

## Instalasi

1. **Persiapan Lingkungan**:
   - Instal PlatformIO IDE atau VS Code dengan ekstensi PlatformIO.
   - Clone atau download proyek ini ke folder PlatformIO Projects.

2. **Instal Library**:
   - Library yang diperlukan sudah tercantum di `platformio.ini`:
     - `marcoschwartz/LiquidCrystal_I2C@^1.1.4`
     - `adafruit/RTClib@^2.1.4`
     - `fmalpartida/LiquidCrystal@^1.5.0`
   - PlatformIO akan menginstal library secara otomatis saat build.

3. **Upload Kode**:
   - Buka proyek di PlatformIO.
   - Build dan upload kode ke Arduino Uno.

## Penggunaan

1. Setelah upload, LCD akan menampilkan pesan sambutan selama 1 detik.
2. Kemudian, layar akan menampilkan waktu real-time dari RTC.
3. Buzzer akan berbunyi setiap detik.
4. Jika RTC kehilangan daya, waktu akan diset ulang ke waktu kompilasi kode.

## Simulasi

Proyek ini dapat disimulasikan di Wokwi:
- Buka `wokwi.toml` di Wokwi editor.
- Jalankan simulasi untuk melihat perilaku jam digital.

## Catatan

- Pastikan modul RTC DS3231 terhubung dengan benar via I2C (A4 SDA, A5 SCL).
- Jika LCD tidak menampilkan apa-apa, sesuaikan kontras menggunakan potensiometer pada pin V0.
- Kode menggunakan LiquidCrystal library untuk interface paralel, bukan I2C.

## Lisensi

Proyek ini dibuat untuk tujuan edukasi. Silakan gunakan dan modifikasi sesuai kebutuhan.

## Kontributor

- Naryama Alvaromadhon Winardi (dari diagram.json)

Jika ada pertanyaan atau saran, silakan buat issue di repository ini.