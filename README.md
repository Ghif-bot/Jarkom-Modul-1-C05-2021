# Jarkom-Modul-1-C05-2021
# Praktikum Modul 1
## 📅 20 September 2021

### 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
**Jawab:**
Pada filter wireshark menuliskan ```http.host contains "ichimarumaru.tech"```

lalu kemudian pada hasil pencarian dilakukan follow TCP stream

kemudian mencari informasi server.

web server yang digunakan adalah nginx/1.18.0 (Ubuntu)

### 2. Temukan paket dari web-web yang menggunakan basic authentication method!
**Jawab:**
Pada bagian filter diisi dengan ```http.authbasic```

### 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
**Jawab:**
Pada wireshark filter mengetikkan ```http contains "basic.ichimarumaru.tech"```

untuk sign in dapat melihat pada bagian Authorization lalu Credentials dimana mengandung username dan password yang dipisahkan dengan titik dua : , dalam kasus ini
username : kuncimenujulautan
password : tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN
setelah login terdapat halaman


lalu mengikuti instruksi yang terdapat pada halaman tersebut.       
**"Sebutkan urutan konfigurasi pengkabelan T568A!
Tuliskan jawaban anda pada kolom di bawah ini. Jangan lupa screenshot lalu masukkan ke laporan. 
(Tombol submit memang nggak ada. Makanya screenshot aja ya)”**



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


pada wireshark filter mengetikkan ```mysql contains "SELECT"```


### 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
**Jawab:**
pada wireshark menulis  ```mysql contains "INSERT"```


lalu terlihat ada statement **INSERT INTO users (username,password) VALUES ("akakanomi",md5("pemisah4lautan"))**
lalu memasukkan username dan password tersebut pada halaman website



lalu setelah login mengisi konfigurasi kabel T568B


dari kiri ke kanan
1. Putih - Oranye         
2. Oranye           
3. Putih - Hijau          
4. Biru               
5. Putih - Biru         
6. Hijau            
7. Putih - Coklat       
8. Coklat             







