# Jarkom-Modul-1-B13-2022

### Kelompok B13
| **No** | **Nama** | **NRP** | 
| ------------- | ------------- | --------- |
| 1 | Amsal Herbert  | 5025201182 | 
| 2 | Elbert Dicky Aristyo | 5025201231 |
| 3 | Nathanael Roviery | 5025201258 |

## Soal 3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!  
Wireshark filter expression: **tcp.dstport == 80**
- Menggunakan display filter **tcp.dstport == 80**
- Setelah itu muncul hasil filter paket menuju port 80

## Soal 6
Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !  
Wireshark filter expression **tcp contains lipi.go.id**

- Menggunakan display filter **tcp contains lipi.go.id**
- Setelah itu muncul paket yang menuju lipi.go.id

## Soal 9
Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam
percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan
kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3
dan simpan output file dengan nama “flag.txt”  
- Mencari percakapan mahasiswa yang bersangkutan dalam pengiriman file dengan display filter **tcp contains "file"**.
- Percakapan dapat dilihat dengan klik kanan paket -> Follow -> TCP Stream.
- Berikut percakapan antar mahasiswa  
[img percakapan]()
- Setelah itu mencari file yang mengandung kata salt dengan menggunakan
display filter tcp.srcport == 9002 && tcp contains "Salt" setelah itu follow
stream dan Save As dengan nama file B13.des3 dan flag.txt


## Soal 10
Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!
Note: Terkait soal nomor 9 dan 10, file yang didapatkan tidak perlu dikumpulkan,
cukup tulis flag yang didapatkan ke dalam laporan kalian.
- Decrypt dengan command **openssl des3 -d -salt -in B13.des3 -out flag.txt**
- Lalu password nama karakter anime kembar 5 yaitu **nakano**
- Setelah itu dapat dilihat hasil decrypt flagnya
