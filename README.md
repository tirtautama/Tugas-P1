# RTOS P1

https://github.com/user-attachments/assets/29cad2e4-44fa-4404-9182-2c25a040bb8d


## Sistem Berbasis STM32 dengan FreeRTOS, ADC, Tampilan OLED, dan Komunikasi UART

Proyek ini mengimplementasikan sistem menggunakan mikrokontroler STM32 dengan FreeRTOS untuk menangani berbagai tugas dan mengelola periferal seperti ADC (Analog-to-Digital Converter), tampilan OLED, dan komunikasi UART.

## Daftar Isi
- [Pendahuluan](#pendahuluan)
- [Fitur](#fitur)
- [Persyaratan Sistem](#persyaratan-sistem)
- [Struktur Proyek](#struktur-proyek)
- [Instalasi dan Pengaturan](#instalasi-dan-pengaturan)
- [Penggunaan](#penggunaan)
- [Lisensi](#lisensi)

## Pendahuluan
Proyek ini menunjukkan penggunaan FreeRTOS pada mikrokontroler STM32 untuk mengelola multitasking dan mengontrol berbagai komponen perangkat keras. Sistem ini dirancang untuk:
- Memantau dan memproses data sensor menggunakan ADC.
- Menampilkan informasi pada layar OLED.
- Berkomunikasi dengan terminal menggunakan UART.
- Mengelola input pengguna melalui interaksi tombol.

## Fitur
- **Multitasking dengan FreeRTOS**: Menangani beberapa tugas seperti membaca sensor, memperbarui tampilan, dan mengelola input pengguna secara efisien.
- **ADC (Analog-to-Digital Converter)**: Membaca data analog dari sensor.
- **Tampilan OLED**: Menampilkan pesan dan nilai sensor menggunakan driver SSD1306.
- **Komunikasi UART**: Berinteraksi dengan terminal untuk menampilkan menu dan data sensor.
- **Penanganan Input Tombol**: Mendeteksi penekanan tombol dan menerapkan logika debounce.

## Persyaratan Sistem
- Papan mikrokontroler STM32 (misalnya, seri STM32F4 atau STM32F7)
- Layar OLED dengan driver SSD1306
- FreeRTOS terintegrasi dengan lingkungan pengembangan STM32
- Periferal I2C, ADC, dan UART dikonfigurasi pada STM32
- STM32CubeIDE atau IDE lain yang kompatibel

## Struktur Proyek
```
/STM32-FreeRTOS-System
    ├── Core/
    │   ├── Src/
    │   │   ├── main.c          # Logika utama program
    │   │   ├── tasks.c         # Implementasi tugas-tugas FreeRTOS
    │   └── Inc/
    │       ├── main.h          # File header untuk program utama
    ├── Drivers/
    │   ├── SSD1306/            # Driver tampilan OLED
    │   ├── HAL_Driver/         # Driver HAL STM32
    └── FreeRTOSConfig/         # File konfigurasi untuk FreeRTOS
```

## Instalasi dan Pengaturan
1. **Kloning Repository**:
   ```bash
   git clone https://github.com/nama-pengguna/STM32-FreeRTOS-System.git
   ```

2. **Buka Proyek di STM32CubeIDE**:
   - Impor proyek ke dalam STM32CubeIDE.
   - Pastikan middleware FreeRTOS dan driver HAL yang diperlukan sudah terinstal.

3. **Konfigurasi Periferal**:
   - Atur I2C untuk komunikasi dengan tampilan OLED.
   - Konfigurasikan UART untuk komunikasi terminal.
   - Inisialisasi ADC untuk pembacaan data sensor.
   - Pastikan pin GPIO untuk tombol dikonfigurasi dengan benar.

4. **Bangun dan Unggah**:
   - Kompilasi proyek.
   - Unggah biner yang sudah dikompilasi ke papan mikrokontroler STM32 Anda.

## Penggunaan
- **Tampilan Informasi**: OLED akan menampilkan pesan awal ("HELLO WORLD :)") dan nilai sensor.
- **Interaksi Tombol**: Tekan tombol untuk memicu fungsi yang berbeda dalam sistem.
- **Menu UART**: Gunakan terminal untuk berinteraksi dengan sistem dan melihat data sensor.

### Detail Tugas
- `defaultTask`: Menginisialisasi dan mengelola sistem.
- `pickButtonTask`: Memantau status tombol dan mengatasi debounce.
- `getADCTask`: Membaca dan memproses data sensor.
- `dispOLEDTask`: Memperbarui informasi pada tampilan OLED.
- `dispUARTTask`: Mengelola komunikasi dengan terminal UART.
