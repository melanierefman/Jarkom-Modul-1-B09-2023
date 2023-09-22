# Praktikum Jarkom Modul 1 Kelompok B09

Anggota Kelompok B09:
| Nama | NRP |
| ---------------------- | ---------- |
| Melanie Sayyidina Sabrina Refman | 5025211029 |
| I Gusti Agung Ngurah Adhi Sanjaya | 5025211056 |

----
## Soal No.1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya
adalah mengunggah suatu file.
- a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?
- b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?
- c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
- d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
### Penyelesaian
a.
- Pertama mendownload capture file dari soal
- Mendownload capture file dan membukanya pada wireshark
- Kemudian filter menggunakan `ftp`
  ![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/bb6dcfa1-39d4-4053-a20a-5a99036ea7f3)
- Lalu setelah keluar packet yang menggunakan protocol ftp, langkah selanjutnya adalah mencari packet yang terdapat request `STOR` yang dimana request ini artinya menggungah sesuatu.
  ![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/58852693-005c-445a-9107-86b2dc3a3c2e)
- Setelah mendapatkan lalu membuka detail `TCP` atau `Transmission Control Protocol` dari packet ini.
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/234ce126-1fa0-490e-b17f-3e15289d48ea)
- Setelah itu kita bisa menemukan Sequence Number (raw) dari packet request `STOR` ini.
- Jawabannya : 258040667
  
b.
- Dengan cara yang sama pada bagian a, kita akan menemukan Acknowledeg number (raw) dari packet ini.
- Jawabannya : 1044861039
  
c.
- Dengan menggunakan cara dari bagian a, kita akan menemukan packet response tepat di bawah packet request `STOR`. 
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/c4927700-0777-43c6-8dac-15f3e0ac9fda)
- Setelah itu gunakan cara yang sama untuk menemukan Sequence Number (raw) dari packet response ini.
  ![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/68971688-dc88-4036-b099-4094425dbd96)
- Jawabannya : 1044861039
  
d.
-  Dengan menggunakan cara dari bagian c, kita dapat menemukan Acknowledget sequence 
(raw) dari packet response ini.
- Jawabannya : 258040696

  
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
  
## Soal No.3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address
adalah 239.255.255.250 dengan port 3702?
b.  Protokol layer transport apa yang digunakan?
### Penyelesaian
a.
- Setelah memasukan capture file, pada soal, gunakan filter `(ip.src ==
239.255.255.250 && udp.port == 3702) || (ip.dst == 239.255.255.250 &&
udp.port == 3702)` yang artinya kita menggunakan 2 kondisi yang parameter
filter nya sama dengan maksud supaya hasil filternya pasti, dengan mencari
paket-paket yang memiliki IP 239.255.255.250 dan udp port 3702. Ini akan
menampilkan semua hasil dari filter yang di tulis pada bagian pojok kanan bawah display wireshark.
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/a9e0f4b7-76e8-4de0-bad0-9bd842377c6b)
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/9e25ef69-daee-4dc2-9d4c-edf9b3186fff)
Jawabannya : 21

b.
-	Protokol ini dapat di lihat pada list packet langsung karena di filter protokolnya langsung ke filter `UDP`.
  ![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/b8b11540-7eed-492d-b239-7a3ece9d7eea)
Jawabannya : UDP

## Soal No.4
Berapa nilai checksum yang didapatkan dari header pada paket nomor 130?
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian pilih paket yang memiliki **No.130**
  
  ![no 4](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/85f6ab06-c7dd-47b2-9bde-26d53506b7a8)
- Kemudian cari data checksum di detail paket (tab bagian bawah)
  
  ![no 4(1)](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/ff11dfdd-9397-4320-a52c-a342ad22aa9c)
- Checksum berada di User Datagram Protocol dan memiliki nilai:**0x18e5**

## Soal No.5
Elshe menemukan suatu file packet capture yang menarik. Bantulah elshe untuk
menganalisis file packet capture tersebut.
- a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
- b.	Port berapakah pada server yang digunakan untuk service SMTP?
- c.	Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
### Penyelesaian
a.
-	Setelah membuka capture file, kita dapat melihat banyak packet yang di capture pada pojok kanan bawah display wireshark
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/275996e2-1c7d-43b4-aade-4381852c12f9)
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/d93bab0b-2c41-45b4-b113-7b70cec89e7b)
Jawabannya : 60

b.
- Jadi karna port yang biasa digunakan untuk service smtp itu merupakan port 25, jadi jawabannya port 25.
Di dalam port 25 ini juga terdapat password untuk membuka isi zip file yang terkunci.
caranya adalah membuka TCP stream dari packet ini
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/dbf99850-a623-497c-8b5c-4463d3bc39b5)
- Lalu kita bisa melihat dan meng-decode password ni dengan Base64 pada internet.
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/e1a1357b-c3c2-4fe5-8f58-ad1765f1098f)
- Setelah itu, kita membuka isi zip dengan password yang telah di decode. Dan berisi nc untuk menjawab pertanyaan no 5 dan mendapatkan flag capture
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/494036e2-95b4-45b7-a57f-0cacb38c1c71)
Jawabannya : 25

c.
-	Pertama kira filter untuk ip addres berikut ` ip.addr && !ip.addr==192.168.1.1 && !ip.addr==192.168.1.2`
-	Lalu setelah mendapatkan hasil filter, hanya tersisisa ip yang berawalan 10.xx.x.x dan 74.xx.xxx.xxx yang dimana dari kedua sisa filter ip ini hanya ip yang berawalan 74 merupakan ip public jadi jawabannya 74.53.140.153
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/7da46371-1eae-4f36-adf7-c47b83347cfd)
Jawabannya : 74.53.140.153

## Soal No.6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT berrsama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan **"server SOURCE ADDRESS 7812 is invalid"**. ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian pilih paket yang memiliki **No.7812** dan ditemukan source addressnya dalah **104.18.14.101**
  
![no 6](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/6fdcaf82-dd18-4ca7-b840-6ba361107462)
- Kemudian solusi dari kode error tersebut didapat dari source addressnya dimana terdiri dari 6 Huruf dengan menggunakan hurus A(1)-R(18)
- Untuk detail penyelesaian solusinya dapat dilihat dari gambar dibawah ini
  
![no 6(1)](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/67472bd0-1cd5-4c25-9930-9a85b9293463)
- Jadi solusi dari kode error tersebut adalah **JDRNJA**

## Soal No.7
Berapa jumlah packet yang menuju IP 184.87.193.88
### Penyelesaian
-	Membuka capture file
-	Lalu filter ip dengan `ip.dst == 184.87.193.88`
-	Lalu jumlah packet hasil filter dapat dilihat pada pojok kanan bawah display wire shark
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/422df6c2-5902-4456-9bd0-47cc27ee6d28)
- Jawabannya : 6

## Soal No. 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)!
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian melakukan filter dengan `tcp.dstport==80||udp.dstport==80`
  
  `tcp.dstport==80` untuk menangkap paket-paket TCP yang ditujukan ke port 80
  
  `udp.dstport==80` untuk menangkap paket-paket UDP yang ditujungan ke port 80
  
  ![no 8](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/5f8ecdb1-7fc3-4c84-9de0-d00740d2bd82)

## Soal No.9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
### Penyelesaian
-	Membuka capture file
-	Lalu filter menggunakan ` ip.src == 10.51.40.1 && ip.dst !=10.39.55.34`
`ip.src == 10.51.40.1`: mengambil hanya lalu lintas yang berasal dari alamat IP
10.51.40.1 sebagai pengirim
`ip.dst != 10.39.55.34`: mengambil lalu lintas yang tidak menuju ke alamat IP
10.39.55.34 sebagai tujuan.
Jadi, kueri ini akan memilih lalu lintas yang berasal dari 10.51.40.1 dan tidak menuju
ke 10.39.55.34.
![image](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87845735/b74c159d-42ef-4ac6-aa81-c8b956df7ad4)
Jawabannya : `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

 
## Soal No. 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet!
### Penyelesaian
- Pertama mendownload capture file dari soal
- Kemudian melakukan filter dengan `telnet`
  
  ![no 10](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/15df35f3-c672-4302-b65a-6dfd6b01390e)
- Kemudian untuk mengecek kredensial yang dimasukkan, dapat dilihat ke bagian Detail Paket (tab bagian bawah)
- Kredensial berada di bagian Telnet dan ditemukan kredensial yang benar seperti gambar dibawah ini
  
  ![no 10(1)](https://github.com/melanierefman/Jarkom-Modul-1-B09-2023/assets/87106838/f88ac2b7-8c02-4192-a019-2b7eea890e91)

## Kendala Pengerjaan Praktikum
- Saat mengakses portal praktikumnya sangat lemot
