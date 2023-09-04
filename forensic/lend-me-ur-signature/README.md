# Lend me your signature

Author: abdierryy

Category: Forensic

Flag: `HCS{N1c3_Th4ts_VerY_Ea5y_R1ghT????}`

## Description
EN : I got sent a waifu image by my friend, but it seems that the image can't be seen. Please help me!

ID : Aku sedang dikirim gambar waifu oleh temanku, tapi sepertinya gambar tersebut tidak bisa dilihat. Tolong bantulah aku!

## Difficulty
Easy (hm)

## Solution

### EN
The first step for me was, look into photo "signatures". Then I found hex signatures, and also HxD.

After downloading HxD, I checked the hex signature of the file and......

![header](images/image_2023-09-03_224603200.png)

At this point I just learned about hex file signatures and figured out that HACKEDHCS is supposed to be the header of a .png file, which is 89 50 4E 47 0D 0A 1A 0A.

After that, I tried downloading TweakPNG (found in the exif and was originally T****PNG, after a bit of google searches I found the app) and opened the file, since it seems well enough, but no! There's an error on something called "IHCS". Then I found out a png file needs to have IEND on the final bit but this was changed to IHCS. I changed the metadata of IHCS to IEND and......

![footer](images/image_2023-09-03_224617667.png)

The image was inputted without errors in TweakPNG.

![newimage](images/waifuimage.png)

To be fair, I was stuck here for quite a while but ended up figuring it out.

On the IHDR menu, we can edit the Width/Height of a png file and at I tried adding +10 to the width (380 to 390) and the flag was seen (half of it). Then I changed the height to 400 and it showed the flag.

![image](https://github.com/Etern1tyDark/hcs-ctf-23/assets/76277790/6913de64-0e65-4d43-981b-66ad7b18a2f2)

![finalimage](chall.png)



### ID
Langkah pertama setelah melihat cara untuk memperbaiki chall.png yaitu - mengecek hex signature

Berikut adalah screenshot dari bagian header image:
![header](images/image_2023-09-03_224603200.png)

Di bagian header terlihat "HACKEDHCS" yang seharusnya merupakan tempat untuk header dari file .png (89 50 4E 47 0D 0A 1A 0A).

Setelah merubah bagian header, gambar bisa dibuka namun ada error terkait IHCS di TweakPNG.

Bagian footer pun saya cek, dan metadata yang seharusnya IEND diubah menjadi IHCS.
![footer](images/image_2023-09-03_224617667.png)

Setelah merubah header dan footer, gambar pun bisa terbuka tanpa error di TweakPNG. (Nama program didapat dari hex signature di bagian footer yang menandakan exif - user comment)

![newimage](images/waifuimage.png)

Kita pun dapat mengubah bagian IHDR, dan menambahkan height, dan flag akan terlihat.

![image](https://github.com/Etern1tyDark/hcs-ctf-23/assets/76277790/6913de64-0e65-4d43-981b-66ad7b18a2f2)

![finalimage](chall.png)
