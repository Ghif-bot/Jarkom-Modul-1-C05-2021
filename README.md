# Jarkom-Modul-1-C05-2021
# Praktikum Modul 1
## 📅 20 September 2021

### 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
**Jawab:**
Pada filter wireshark menuliskan ```http.host contains "ichimarumaru.tech"```
<img src="screenshot/nomer-1-filter.jpg" width="800">       
lalu kemudian pada hasil pencarian dilakukan **follow TCP stream**
<img src="screenshot/nomer-1-folo.jpg" width="800">                     
kemudian mencari informasi server.
<img src="screenshot/nomer1-server.jpg" width="800">            
web server yang digunakan adalah nginx/1.18.0 (Ubuntu)

### 2. Temukan paket dari web-web yang menggunakan basic authentication method!
**Jawab:**
Pada bagian filter diisi dengan ```http.authbasic```
<img src="screenshot/nomer2.jpg" width="800">   

### 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
**Jawab:**
Pada wireshark filter mengetikkan ```http contains "basic.ichimarumaru.tech"```
<img src="screenshot/nomer 3.jpg" width="800">         
untuk sign in dapat melihat pada bagian **Authorization** lalu **Credentials** dimana mengandung username dan password yang dipisahkan dengan titik dua : , dalam kasus ini           
**username : kuncimenujulautan**                        
**password : tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN**             
setelah login terdapat halaman
<img src="screenshot/nomer3_2.jpg" width="800">           
lalu mengikuti instruksi yang terdapat pada halaman tersebut.       
**"Sebutkan urutan konfigurasi pengkabelan T568A!
Tuliskan jawaban anda pada kolom di bawah ini. Jangan lupa screenshot lalu masukkan ke laporan. 
(Tombol submit memang nggak ada. Makanya screenshot aja ya)”**
<img src="screenshot/nomer3_3.jpg" width="800">                           
Urutan ke 1 : Putih Hijau              
Urutan ke 2 : Hijau                     
Urutan ke 3 : Putih Orange            
Urutan ke 4 : Biru                      
Urutan ke 5 : Putih Biru              
Urutan ke 6 : Orange                
Urutan ke 7 : Putih Coklat              
Urutan ke 8 : Coklat                  

### 4. Temukan paket mysql yang mengandung perintah query select!
**Jawab:**
pada wireshark filter mengetikkan ```mysql contains "select"```
<img src="screenshot/nomer4_select.jpg" width="800">            
pada wireshark filter mengetikkan ```mysql contains "SELECT"```
<img src="screenshot/nomer4_select-besar.jpg" width="800">    


### 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
**Jawab:**
pada wireshark menulis  ```mysql contains "INSERT"```
<img src="screenshot/nomer5.jpg" width="800">    
lalu terlihat ada statement **INSERT INTO users (username,password) VALUES ("akakanomi",md5("pemisah4lautan"))**
lalu memasukkan username dan password tersebut pada halaman website               
<img src="screenshot/nomer5-login.jpg" width="250">                            
lalu setelah login mengisi konfigurasi kabel T568B
<img src="screenshot/nomer5_isijawaban.jpg" width="800">    
dari kiri ke kanan
1. Putih - Oranye         
2. Oranye           
3. Putih - Hijau          
4. Biru               
5. Putih - Biru         
6. Hijau            
7. Putih - Coklat       
8. Coklat             

### 6. Cari username dan password ketika melakukan login ke FTP Server!
**Jawab:**
Langkah:
Menghidupkan Wireshark dan filter dengan keyword “ftp.request.command == PASS || ftp.request.command == USER”
Hasil:
<img src="screenshot/nomer6.png" width="800"> 

### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
**Jawab:**

Langkah

->Pada bagian filter menuliskan ftp-data contains "Real.pdf"
<img src="screenshot/nomer7-filter.png" width="800"> 

-> lalu dari kedua paket yang muncul, dapat dipilih salah satu untuk kemudian di klik kanan pada paket tersebut kemudian follow-> TCP Stream
<img src="screenshot/nomer7-ascii.png" width="800"> 

-> setelah itu pada bagian show data as diubah dari ASCII ke format RAW lalu di Save as … dengan nama file misal nomer7 dan berekstensi zip
<img src="screenshot/nomer7-raw.png" width="800"> 

-> setelah itu membuka file hasil download tersebut
<img src="screenshot/nomer7-zip.png" width="800"> 

-> kemudian saat dibuka filenya akan menampilkan halaman berikut
<img src="screenshot/nomer7-pdf.png" width="800"> 


### 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
**Jawab:**

Pada filter yang digunakan yaitu ftp.request.command == STOR dimana akan mencari data file yang di upload dari ftp tersebut
<img src="screenshot/nomer8.png" width="800"> 

Pada filter yang digunakan yaitu ftp.request.command == RETR dimana akan mencari data file yang di downlaod dari ftp tersebut
<img src="screenshot/nomer8-retr.png" width="800"> 

### 9. Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
**Jawab:**

Langkah

-> Pada filter mengetikkan ftp-data.command contains "secret.zip"
<img src="screenshot/nomer9-filter.png" width="800"> 

-> Kemudian follow TCP Stream pada salah satu hasil
<img src="screenshot/nomer9-ascii.png" width="800"> 

-> Kemudian ubah data dari ASCII menjadi RAW kemudian save as .zip
<img src="screenshot/nomer9-raw.png" width="800"> 
<img src="screenshot/nomer9-zip.png" width="800"> 

-> Ketika dibuka masih ada yang perlu diproses
<img src="screenshot/nomer9-password.png" width="800"> 


### 10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
**Jawab:**

Langkah

-> Pada filter wireshark menuliskan ftp-data contains "history" 
<img src="screenshot/nomer10-history.png" width="800"> 

-> Follow TCP yang di tuju
<img src="screenshot/nomer10-isi-history.png" width="800"> 

-> Pada bagian line-based terdapat beberapa tulisan seperti “bukanapaapa.txt” lalu ftp-data.command contains "bukanapaapa" 
<img src="screenshot/nomer10-bukanapaapa.png" width="800"> 

-> passwordnya adalah d1b1langbukanapaapajugagapercaya
<img src="screenshot/nomer10-password.png" width="800"> 

-> lalu saat dimasukkan passwordnya ke file Wanted.pdf
<img src="screenshot/nomer10-isi-pdf.png" width="800"> 




### 11.
**Jawab:**

Langkah
-> Pada filter mengetikkan  ```tcp src port 80``` untuk mengambil paket yang berasal dari port 80

Hasil: 


### 12.
**Jawab**


### 13.
**Jawab:**

Langkah
-> Pada filter mengetikkan ```dst port 443``` untuk menampilkan paket yang menuju port 443

Hasil


### 14.
**Jawab**



### 15.
**Jawab**





