# Praktikum Jarkom Modul 1 Kelompok B09

Anggota Kelompok B09:
| Nama | NRP |
| ---------------------- | ---------- |
| Melanie Sayyidina Sabrina Refman | 5025211029 |
| I Gusti Agung Ngurah Adhi Sanjaya | 5025211056 |

----

## Soal No.2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian melakukan filter dengan `http`
  ![no 2](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/4aa59879-0494-4cbb-8fa1-e8a8f9632e4f)
- Kemudian pilih salah satu paket dengan protocol **HTTP** dengan klik kanan, pilih **Follow**
- Klik **HTTP Stream**, kemudian akan muncul windown seperti dibawah ini
  ![no 2(1)](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/c9500a96-c405-4bcc-b416-d19ccb65a371)
- Kemudian ditemukan web servernya adalah **gunicorn**

## Soal No.4
Berapa nilai checksum yang didapatkan dari header pada paket nomor 130?
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian pilih paket yang memiliki **No.130**
  ![no 4](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/85f6ab06-c7dd-47b2-9bde-26d53506b7a8)
- Kemudian cari data checksum di detail paket (tab bagian bawah)
  ![no 4(1)](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/ff11dfdd-9397-4320-a52c-a342ad22aa9c)
- Checksum berada di User Datagram Protocol

## Soal No. 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)!
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian melakukan filter dengan `tcp.dstport==80||udp.dstport==80`
  `tcp.dstport==80` untuk menangkap paket-paket TCP yang ditujukan ke port 80
  `udp.dstport==80` untuk menangkap paket-paket UDP yang ditujungan ke port 80
  ![no 8](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/5f8ecdb1-7fc3-4c84-9de0-d00740d2bd82)
 
## Soal No. 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet!
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian melakukan filter dengan `telnet`
  ![no 10](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/15df35f3-c672-4302-b65a-6dfd6b01390e)
- Kemudian untuk mengecek kredensial yang dimasukkan, dapat dilihat ke bagian Detail Paket (tab bagian bawah)
- Kredensial berada di bagian Telnet dan ditemukan kredensial yang benar seperti gambar dibawah ini
  ![no 10(1)](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/f88ac2b7-8c02-4192-a019-2b7eea890e91)
