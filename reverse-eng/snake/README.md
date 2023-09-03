# Snake 
### me when snake
Author: kosong

Category: Reverse Engineering

Flag: `HCS{ez_game_right?_74ab}`

## Description
Capai skor tertentu untuk mendapatkan flag.

## Difficulty
Easy

## Solution
Langkah pertama yang saya buat yaitu menjalankan `index.html`, setelah mengetahui bahwa ini adalah game snake yang simple, saya melihat ke `app.js`.

Saya melihat kode di `app.js` satu persatu dan menemukan dua hal yang penting yaitu :
1. playerScore==0x539&&win()
2. playerScore=0x0

![image](https://github.com/Etern1tyDark/hcs-ctf-23/assets/76277790/5dafbb9a-cff5-4252-b148-7a99eb3c4c8d)

Disini saya menyadari bahwa saya hanya perlu merubah playerScore di bagian kanan menjadi 0x539 -> 1337 dalam decimal dan itu seharusnya menampilkan flag.

![image](https://github.com/Etern1tyDark/hcs-ctf-23/assets/76277790/c70bcfd0-2177-4145-8ba8-c432439bb205)
