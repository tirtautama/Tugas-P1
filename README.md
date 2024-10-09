# RTOS P1

https://github.com/user-attachments/assets/29cad2e4-44fa-4404-9182-2c25a040bb8d



# Praktikum STM32 dengan FreeRTOS dan Tampilan Data di PuTTY

Praktikum ini mengimplementasikan sebuah sistem berbasis STM32 yang menggunakan FreeRTOS untuk multitasking, memantau sensor menggunakan ADC (Analog-to-Digital Converter), serta berkomunikasi dengan pengguna melalui antarmuka serial menggunakan UART dan PuTTY.

## Fitur Utama
- **Multitasking dengan FreeRTOS**: Sistem operasi real-time yang memungkinkan beberapa task berjalan secara paralel.
- **Sensor Monitoring**: Pembacaan data sensor menggunakan ADC yang dikonversi dan ditampilkan secara real-time.
- **Antarmuka Pengguna via UART**: Menu interaktif ditampilkan di terminal PuTTY, memungkinkan pengguna untuk memilih dan memantau tegangan sensor.
- **Debouncing Tombol**: Implementasi debouncing untuk memastikan tombol tidak terbaca lebih dari sekali saat ditekan.

## Perangkat Keras yang Digunakan
- STM32 Microcontroller
- Sensor analog yang terhubung ke ADC
- Komunikasi serial UART untuk antarmuka dengan PuTTY
- Tombol tekan untuk kontrol input pengguna

## Prasyarat
- **STM32CubeMX**: Untuk konfigurasi dan inisialisasi perangkat keras.
- **Keil uVision atau IDE STM32 lainnya**: Untuk pengembangan dan kompilasi kode.
- **PuTTY atau terminal serial lainnya**: Untuk komunikasi serial melalui UART.

## Instalasi
1. **Konfigurasi Hardware**: Hubungkan sensor ke port ADC pada STM32 dan siapkan tombol sebagai input.
2. **Setup UART**: Hubungkan STM32 ke komputer melalui port serial untuk berkomunikasi dengan PuTTY.
3. **Konfigurasi FreeRTOS**: Sesuaikan pengaturan task dan prioritas sesuai kebutuhan Anda.

## Cara Menggunakan
1. **Inisialisasi Sistem**: Setelah sistem menyala, program akan memulai task FreeRTOS dan menampilkan menu awal di PuTTY.
2. **Navigasi Menu di PuTTY**:
   - Pilih opsi yang tersedia untuk memantau data sensor atau menampilkan kembali menu.
3. **Pemantauan Sensor**: Data sensor akan diperbarui secara real-time dan ditampilkan melalui terminal PuTTY.

## Task Utama dalam FreeRTOS
- `defaultTask`: Menjalankan tugas dasar sistem.
- `pickButtonTask`: Memantau status tombol dan melakukan aksi sesuai input.
- `getADCTask`: Membaca data dari sensor menggunakan ADC.
- `dispUARTTask`: Menampilkan data sensor ke terminal PuTTY melalui UART.

## Struktur Proyek
- `main.c`: Berisi logika utama dan pengaturan task FreeRTOS.
- `adc.c`: Konfigurasi untuk pembacaan data dari sensor.
- `uart.c`: Menangani komunikasi serial dengan PuTTY.
- `freertos.c`: Pengaturan task dan manajemen multitasking.

