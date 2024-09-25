![Screenshot 2024-09-25 105538](https://github.com/user-attachments/assets/f329e957-d3fe-4c9a-af9e-2f94f28366f8)1.Eksekusi seluruh profile yang ada :

a. Edit file profile /etc/profile dan tampilkan pesan sebagai berikut :
echo “Profile dari /etc/profile”

![Screenshot 2024-09-25 095156](https://github.com/user-attachments/assets/5809b2ed-cf7a-4b88-831c-6b9dbc7b67e8)

b. Asumsi nama anda stD02001, maka edit semua profile yang ada yaitu :
/home/stD02001/.bash_profile
/home/. stD02001/.bash_login
/home/mahasiswa/.profile
/home/mahasiswa/.bashrc
Ganti nama /home/mahasiswa dengan nama anda sendiri. Pada setiap
file tersebut, cantumkan instruksi echo, misalnya pada /home/ mahasiswa/.bash_profile :
echo “Profile dari .bash_profile”
Lakukan hal yang sama untuk file lainnya, sesuaikan tampilan dengan nama file yang
bersangkutan.

![Screenshot 2024-09-25 084127](https://github.com/user-attachments/assets/67edb4bf-e33e-4d7f-aa01-37d7eb7400b2)

![Screenshot 2024-09-25 084006](https://github.com/user-attachments/assets/06f0c09b-a16c-47a4-98b8-eed7b0ca5f78)

![Screenshot 2024-09-25 084509](https://github.com/user-attachments/assets/34501b2e-87d4-4f83-aa34-5ba2b12694d8)

![Screenshot 2024-09-25 084330](https://github.com/user-attachments/assets/d44def76-e20a-4da3-b6ec-d5c316d7689d)

![Screenshot 2024-09-25 100227](https://github.com/user-attachments/assets/33376200-d696-4a5b-9707-7e7d2395e17c)

![Screenshot 2024-09-25 100852](https://github.com/user-attachments/assets/e1646092-533a-4b5e-931f-e4ff5bd01a40)

c. Jalankan instruksi subtitute user (su dan su -), kemudian keluar dengan perintah exit. Caranya :

![Screenshot 2024-09-25 101050](https://github.com/user-attachments/assets/c51aa891-c0be-4d47-b14b-7df33dbf5854)

![Screenshot 2024-09-25 101202](https://github.com/user-attachments/assets/c507eb0c-1b50-4dae-89b5-b0f7c0af4058)

![Screenshot 2024-09-25 101215](https://github.com/user-attachments/assets/4204328d-fd14-4303-a0e9-cc1268f4e3b5)

Perbedaan dari kedua utilitas tersebut adalah, utilitas su untuk mengganti user tanpa mengubah environment, sedangkan su - untuk mengganti user dengan memuat environment (profile) dari user tersebut

2.Prompt String (PS)

a. Edit file .bash_profile, ganti prompt PS1 dengan ‘>’. Instruksi export diperlukan dengan parameter nama variable tersebut, agar perubahan variable PS1 dikenal oleh semua shell

 PS1='> '

 export PS1

b. Eksperimen hasil PS1 :

 $ PS1=“\! > “

 69 > PS1=”\d > “

 Mon Sep 23 > PS1=”\t > “

 10:10:20 > PS1=”Saya=\u > “

 Saya=mahasiswa > PS1=”\w >”

 ~ > PS1=\h >”

 Jawab :

a. Untuk mengedit file .bash_profile, kita bisa menggunakan command nano. Cara nya kita ketik nano /home/nama user/.bash_profile

![Screenshot 2024-09-25 101422](https://github.com/user-attachments/assets/15af6ff6-31a4-45cc-83bf-1566bbc29b20)

Kemudian kita tambahkan PS1='> ', ini untuk mengganti command PS1 dengan '>', lalu dibawahnya kita tambahkan export PS1, agar perubahan variable PS1 dikenal oleh semua shell

![Screenshot 2024-09-25 101532](https://github.com/user-attachments/assets/af133d8e-ba81-429d-9538-c634e5fd5483)

Jangan lupa di save

b. Kemudian kita jalankan beberapa command PS1 berikut :

- PS1='\! > ' (untuk menampilkan nomor perintah)

- PS1='\d > ' (untuk menampilkan tanggal)

- PS1='\t > ' (untuk menampilkan waktu)

- PS1='Saya=\u > ' (untuk menampilkan username)

- PS1='\w >' (untuk menampilkan direktori kerja saat ini)

- PS1='\h >' (untuk menampilkan hostname)

![Screenshot 2024-09-25 102949](https://github.com/user-attachments/assets/aa64dc0d-6c6d-48f3-ac2e-caff37b2bf9d)

3.Logout

Edit file .bash_logout, tampilkan pesan dan tahan selama 5 detik, sebelum eksekusi logout.

Echo “Terima kasih atas sesi yang diberikan”

Sleep 5

clear

Jawab :

Untuk mengedit file .bash_logout, kita menggunakan command nano. Caranya kita ketik nano /home/nama user/.bash_logout

![Screenshot 2024-09-25 103342](https://github.com/user-attachments/assets/46baa7eb-c31c-4892-9292-8e3986ea294a)

Setelah itu kita tambahkan command echo "Terima kasih atas sesi yang diberikan", kemudian di bawahnya sleep 5, dan dibawahnya lagi clear

![Screenshot 2024-09-25 103328](https://github.com/user-attachments/assets/00154681-718f-47ad-b4be-6e6d2a748a61)

command-command di atas berfungsi untuk menampilkan pesan "Terima kasih atas sesi yang diberikan", lalu menahan layar selama 5 detik agar pesan dapat terlihat sebelum terminal menutup sesi, dan kemudian membersihkan terminal setelah pesan ditampilkan.

Untuk melihat pesan tersebut, kita harus login dulu menggunakan command su -. Caranya kita ketik su - nama user, setelah itu kita gunakan command exit untuk logout dan pesan pun ditampilkan

![Screenshot 2024-09-25 103513](https://github.com/user-attachments/assets/7509219f-1b72-4e89-a125-4c73e3abfae9)

Setelah 5 detik, terminal akan dibersihkan.

4.Bash script

a. Buat 3 buah script p1.sh, p2.sh, p3.sh dengan isi masing-masing :

p1.sh

#! /bin/bash

echo “Program p1”

ls –l

p2.sh

#! /bin/bash

echo “Program p2”

who

p3.sh

#! /bin/bash

echo “Program p3”

ps x

b. Jalankan script tersebut sebagai berikut :

$ ./p1.sh ; ./p3.sh ; ./p2.sh

$ ./p1.sh &

$ ./p1.sh & ./p2.sh & ./p3.sh &

$ ( ./p1.sh ; ./p3.sh ) &

Jawab :

a. Untuk membuat script p1.sh, p2.sh, dan p3.sh, kita bisa menggunakan command nano, kemudian isi dengan command yang sudah ada di soal. Caranya bisa dilihat dari gambar berikut :

- untuk p1.sh

![Screenshot 2024-09-25 104309](https://github.com/user-attachments/assets/656b8234-e282-44e2-8575-86096214c6f9)

- untuk p2.sh

![Screenshot 2024-09-25 104540](https://github.com/user-attachments/assets/bb9900c5-f4c7-405f-b546-aa588585b2c4)

- untuk p3.sh

![Screenshot 2024-09-25 104642](https://github.com/user-attachments/assets/569b127a-a715-4241-89ee-9827b896b27c)

b. Lalu jalankan script tersebut dengan cara sebagai berikut :

sebelum itu kita ubah dulu script menjadi executable dengan menggunakan command chmod +x. Caranya :    

![Screenshot 2024-09-25 104745](https://github.com/user-attachments/assets/a4cee53b-908b-4b1c-86eb-98229ac2ea4d)

 - ./p1.sh ; ./p3.sh ; ./p2.sh (untuk menjalankan script secara berurutan)

![Screenshot 2024-09-25 105038](https://github.com/user-attachments/assets/86e33ef4-b598-485c-b8b5-47bf0a86b965)

 - ./p1.sh & (untuk menjalankan script di background)

![Screenshot 2024-09-25 105144](https://github.com/user-attachments/assets/4bbe791f-be16-4be1-8987-1e1d9802f1b8)

 - ./p1.sh & ./p2.sh & ./p3.sh & (untuk menggabungkan foreground dan background)

![Screenshot 2024-09-25 105538](https://github.com/user-attachments/assets/b599230e-2b38-4883-b1af-6e8b4532ed2f)

 - ( ./p1.sh ; ./p3.sh ) & (untuk menjalankan beberapa script dalam satu block)

![Screenshot 2024-09-25 105654](https://github.com/user-attachments/assets/01e34a82-45f4-413e-a877-8441498298f9)

5.Jobs

a. Buat shell-script yang melakukan loop dengan nama pwaktu.sh, setiap 10 detik, kemudian menyimpan tanggal dan jam pada file hasil.

#!/bin/bash

while [ true ]

do

 date >> hasil

 sleep 10

done

b. Jalankan sebagai background; kemudian jalankan satu program (utilitas find) di background sebagai berikut :

$ jobs

$ find / -print > files 2>/dev/null &

$ jobs

c. Jadikan program ke 1 sebagai foreground, tekan ^Z dan kembalikan program tersebut ke background

$ fg %1

$ bg

d. Stop program background dengan utilitas kill

$ ps x

$ kill [Nomor PID]

Jawab :

a. Pertama-tama kita buat shell-script dengan nama pwaktu.sh, dengan menggunakan command nano

![Screenshot 2024-09-25 105834](https://github.com/user-attachments/assets/384a7890-ca4e-46fc-9738-edb7d7cc6394)

Command atau script pada gambar itu untuk menciptakan loop tak terhingga yang mencatat tanggal dan waktu saat ini ke dalam file bernama hasil setiap 10 detik. Output ditambahkan ke file tanpa menghapus isi yang sudah ada, sehingga file tersebut terus diperbarui dengan waktu baru.

b. buat shell-script diatas menjadi executable, dangan menggunakan command chmod +x pwaktu.sh

![Screenshot 2024-09-25 105918](https://github.com/user-attachments/assets/99eb5e85-181d-4a23-bf70-bf4fb1315e79)

Kemudian jalankan script di background

![Screenshot 2024-09-25 105941](https://github.com/user-attachments/assets/59108c65-68a2-4811-8c0e-3988323144ee)

Lalu jalankan perintah berikut :

-jobs

-find / -print > files 2>/dev/null &

-jobs

![Screenshot 2024-09-25 110050](https://github.com/user-attachments/assets/a0bab5fa-c00a-48b9-8580-1b1177d4037b)

Command jobs digunakan untuk melihat daftar proses yang berjalan di bakground, dan command find / -print > files 2>/dev/null & mencari semua file dan direktori mulai dari root (/), menyimpan hasilnya dalam file bernama files, dan mengabaikan pesan kesalahan dengan mengarahkan output kesalahan ke /dev/null. Dengan penggunaan &, perintah ini dijalankan di latar belakang, memungkinkan pengguna untuk tetap menggunakan terminal selama proses pencarian berlangsung.

c. Lalu kita gunakan command berikut :

-fg %1

-bg

![Screenshot 2024-09-25 110157](https://github.com/user-attachments/assets/7dbc7e3a-7125-4642-a123-0934fb43e4d6)

Command fg adalah untuk membawa proses dari background ke foreground, dimana %1, nomor 1 adalah proses dari pwaktu.sh, yang berarti command diatas membawa proses pwaktu.sh dari background ke foreground. Lalu, untuk menghentikan prosesnya, kita bisa tekan ctrl + z. Kemudian kita menggunakan command bg, yang dimana command tersebut untuk mengembalikan proses pwaktu.sh itu ke background kembali

d. Untuk menyetop program background, kita bisa menggunakan command kill. Tapi kita harus mencari nomor PID nya terlebih dahulu. Caranya kita bisa menggunakan command ps x

![Screenshot 2024-09-25 110226](https://github.com/user-attachments/assets/3da21e1c-236e-4eb8-8d59-f80a079a2156)

![Screenshot 2024-09-25 110302](https://github.com/user-attachments/assets/4046d58f-f14c-42b4-8298-3af2cdeca125)

Bisa kita lihat kalau digambar menampilkan daftar proses yang sedang berjalan di back ground dan nomor PID nya (nomor PID itu yang paling kiri). Sekarang kita coba hapus salah satu proses background dari pwaktu.sh dangan nomor PID 11615, caranya kita ketik kill 11615

![Screenshot 2024-09-25 110302](https://github.com/user-attachments/assets/76c585a2-f349-42f6-aad8-4e7822d0efeb)

Untuk melihat apakah proses tersebut sudah di kill atau si stop, kita pakai command ps x lagi saja

![Screenshot 2024-09-25 110441](https://github.com/user-attachments/assets/46f27ce0-a115-4947-b654-ef0f7cc09104)

Bisa kita lihat kalau ada tulisan Terminated ./pwaktu.sh, yang berarti proses nya sudah di stop

6.History

a. Ganti nilai HISTSIZE dari 1000 menjadi 20

$ HISTSIZE=20

$ history

b. Gunakan fasilitas history dengan mengedit instruksi baris ke 5 dari instruksi yang terakhir dilakukan

$ !-5

c. Ulangi instruksi yang terakhir. Gunakan juga ^P dan ^N untuk bernavigasi pada history bufer

$ !!

d. Ulangi instruksi pada history bufer nomor 150

$ !150

e. Ulangi instruksi dengan prefix “ls”

$ !ls

Jawab :

a. Untuk mengganti HISTSIZE yang awalnya 1000 menjadi 20, kita bisa menggunakan command HISTSIZE=20, fungsinya adalah ketika menggunakan command history untuk melihat daftar history atau riwayat comman- command yang kita gunakan sebelumnya, yang ditampilkan hanyalah 20 daftar saja yang awalnya 1000.

![Screenshot 2024-09-25 110523](https://github.com/user-attachments/assets/e66dc465-0470-46e5-9941-2cb7ead2c8c5)

b. Command !-4 berfungsi untuk melihat history nomor 4 dari yang paling terkhir, dan bisa kita lihat di daftar history di atas, nomor 4 dari terakhir adalah HISTSIZE=20, maka output yang ditampilkan adalah HISTSIZE=20

![Screenshot 2024-09-25 110850](https://github.com/user-attachments/assets/c48cfb54-cd64-43d3-a62d-d470d97dd142)

d. Untuk melihat history nomor 150, kita bisa menggunakan command !150

![Screenshot 2024-09-25 111003](https://github.com/user-attachments/assets/afd5ffde-4b51-4e59-a71e-0322403009ec)

Bisa kita lihat di gambar diatas, ada tulisan event not found. Itu dikarenakan history nomor 150 tidak ada di dalam 20 daftar history yang sudah ditampilkan pada bagian a. Namun jika saya menggunakan nomor yang ada didalam daftar history, misalnya nomor 327, yang dimana merupakan history dari ps x, maka itu akan mengulangi command atau instruksi dari ps x dan outputnya juga

![Screenshot 2024-09-25 111126](https://github.com/user-attachments/assets/1470b445-4f07-4d76-b489-70a78a5716d2)

e. Untuk mengulangi instruksi dari command ls, kita bisa menggunakan command !ls

![Screenshot 2024-09-25 111153](https://github.com/user-attachments/assets/90a37440-7eab-48e7-9ba6-56dad209c4be)

Bisa kita lihat, lagi-lagi event not found. Sama seperti sebelumnya, itu berarti command ls tidak ada didalam 20 daftar history. Kalau begitu saya akan menggunakan command ls supaya ada didalam daftar history

![Screenshot 2024-09-25 111252](https://github.com/user-attachments/assets/b290328c-9c98-428e-afdd-3b08b61ca6cc)

Bisa kkta lihat, command ls sudah ada didalam daftar history, yaitu di nomor 333

Nah, karena sudah ada didalam daftar, itu berarti kita bisa mengulang command ls dengan menggunakan !ls

![Screenshot 2024-09-25 111330](https://github.com/user-attachments/assets/9d0fcb83-b3a1-4ff1-953e-b70a9138bb6a)













































