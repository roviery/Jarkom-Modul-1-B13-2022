# Jarkom-Modul-1-B13-2022

### Kelompok B13
| **No** | **Nama** | **NRP** | 
| ------------- | ------------- | --------- |
| 1 | Amsal Herbert  | 5025201182 | 
| 2 | Elbert Dicky Aristyo | 5025201231 |
| 3 | Nathanael Roviery | 5025201258 |

## Soal 1
Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!
- Menggunakan display filter tcp contains monta.if.its.ac.id
- Lalu klik kanan dan pilih follow tcp stream dari salah satu package untuk mendapat informasi tentang web server yang digunakan.
didapatkan informasi server yaitu **nginx/1.10.3**
![soal-1-1](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal1-1.png)
![soal-1-2](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal1-2.png)

## Soal 2
Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?

Wireshark filter expression: **http matches "detailtopik"** 

Digunakan display filter ini untuk mencari paket http yang menampilkan kata kunci “detailtopik”.
![soal-2-1](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-2-1.png)

Sesuai hasil dari display, Judul TA yang dibuka adalah Evaluasi unjuk kerja User Space Filesystem (FUSE).
![soal-2-2](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-2-2.png)

## Soal 3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!  
Wireshark filter expression: **tcp.dstport == 80**
- Menggunakan display filter **tcp.dstport == 80**
- Setelah itu muncul hasil filter paket menuju port 80
![soal-3](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-3.jpg)

## Soal 4
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

Wireshark filter expression: **tcp.port == 21 || udp.port == 21**

Digunakan srcport untuk filter paket berdasarkan port asal (source)
![soal-4](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal4.png)

## Soal 5
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

Wireshark filter expression: **udp.srcport == 443 || tcp.srcport == 443**

Digunakan srcport untuk filter paket berdasarkan port asal (source) 
![soal-5](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-5.png)

## Soal 6
Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !  
Wireshark filter expression **tcp contains lipi.go.id**

- Menggunakan display filter **tcp contains lipi.go.id**
- Setelah itu muncul paket yang menuju lipi.go.id
![soal-6](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-6.jpg)

## Soal 7
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
- gunakan CMD untuk menampilkan alamat IP yang sedang digunakan, jalankan perintah ipconfig. Dan didapatkan alamat IPv4 adalah *192.168.18.66*

![soal-7-1](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal7-1.png)

- pada captures filter gunakan **src host 192.168.137.49**.

Pada pengerjaan saat praktikum, saya mengganti wifi sehingga ada perbedaan alamat IP dalam jawaban ini
![soal-7-2](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal7-2.png)

- lalu didapatkan info 
![soal-7-3](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal7-3.png)

## Soal 8
Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.

Percakapan kecurangan dapat dicari dengan tcp matches “jawaban” dan dilihat satu persatu dengan klik kanan paket → Follow → TCP Stream atau display filter tcp.stream eq 12.
![soal-8-1](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-8-1.png)
![soal-8-2](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-8-2.png)

## Soal 9
Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam
percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan
kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3
dan simpan output file dengan nama “flag.txt”  
- Mencari percakapan mahasiswa yang bersangkutan dalam pengiriman file dengan display filter **tcp contains "file"**.
- Percakapan dapat dilihat dengan klik kanan paket -> Follow -> TCP Stream.
- Berikut percakapan antar mahasiswa  
![soal-9-1](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-9-1.jpg)
- Setelah itu mencari file yang mengandung kata salt dengan menggunakan
display filter tcp.srcport == 9002 && tcp contains "Salt" setelah itu follow
stream dan Save As dengan nama file B13.des3 dan flag.txt  
![soal-9-2](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-9-2.jpg)


## Soal 10
Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!
Note: Terkait soal nomor 9 dan 10, file yang didapatkan tidak perlu dikumpulkan,
cukup tulis flag yang didapatkan ke dalam laporan kalian.
- Decrypt dengan command **openssl des3 -d -salt -in B13.des3 -out flag.txt**
- Lalu password nama karakter anime kembar 5 yaitu **nakano**
- Setelah itu dapat dilihat hasil decrypt flagnya
![soal-10](https://github.com/roviery/Jarkom-Modul-1-B13-2022/blob/master/img/soal-10.jpg)
