# Jarkom-Modul-4-E05-2021-

Nama Kelompok:
1. Muhammad Rafki Mardi 05111940000054
2. Hana Machmudah 05111940000072
3. Achmad Fadillah  05111940000155

<img width="1837" alt="topologi" src="https://user-images.githubusercontent.com/66562311/143669711-57c1dd6a-39de-4172-a5b4-a1a720fe7775.PNG">

Pada praktikum ini dilakukan pembagian CLASSESS yang berbeda, pada CPT menggunakan VLSM dan GNS3 menggunakan CIDR.

## VLSM
1. Melakukan pembagian subnet pada topologi.

   ![Shift 4](https://user-images.githubusercontent.com/66562311/143605413-4a62f933-0cbc-49dd-bc2b-58a522e787fa.jpg)
   
2. Mentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.
   
   ![VLSM_Labelling subnet](https://user-images.githubusercontent.com/66562311/143669366-f8885d10-0798-4211-85ec-6319491d31c7.jpg)
   
3. Melakukan perhitungan pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon. Melakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada.

   ![VLSM_pohon](https://user-images.githubusercontent.com/66562311/143669868-43932927-fafb-4a6f-9136-aaadda2ed81c.jpg)

4. Didapatkan pembagian IP dari pohon tersebut sebagai berikut.

   ![VLSM_pembagianIP](https://user-images.githubusercontent.com/66562311/143669345-c7469fbb-761b-4606-a069-d9c0df0f9c34.jpg)
   
5. Mengatur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM.
- FOOSHA (sebagai Router)
     mengatur IP pada interface FOOSHA yang mengarah ke CLOUD

     <img width="700" alt="FOOSHA ke CLOUD" src="https://user-images.githubusercontent.com/66562311/143670217-17cb7250-4027-4a72-8d8b-dd7e8574b363.PNG">

     mengatur IP pada interface FOOSHA yang mengarah ke BLUENO

     <img width="700" alt="FOOSHA ke BLUENO" src="https://user-images.githubusercontent.com/66562311/143670238-3faaeabc-0d44-4027-9ae0-dcc1326e13e4.PNG">

     mengatur IP pada interface FOOSHA yang mengarah ke DORIKI

     <img width="700" alt="FOOSHA ke DORIKI" src="https://user-images.githubusercontent.com/66562311/143670269-4571aed1-4879-4e0d-93e1-018f09bc6fa1.PNG">

     mengatur IP pada interface FOOSHA yang mengarah ke WATER7

     <img width="700" alt="FOOSHA ke WATER7" src="https://user-images.githubusercontent.com/66562311/143670276-3e138017-e4f6-4c68-a885-1e1f59f201f5.PNG">

     mengatur IP pada interface FOOSHA yang mengarah ke GUANHO

     <img width="700" alt="FOOSHA ke GUANHO" src="https://user-images.githubusercontent.com/66562311/143670290-2a9e53e9-f363-4945-b4f1-e7d33cd254d5.PNG">

     Melakukan routing pada FOOSHA

     <img width="700" alt="FOOSHA routing" src="https://user-images.githubusercontent.com/66562311/143670476-4960ac73-a037-4dda-8c41-8ddae7c700f0.PNG">

     ```
     192.202.8.0/22 via 192.202.8.2
     192.202.12.0/22 via 192.202.27.154
     192.202.27.172/30 via 192.202.27.174
     192.202.0.0/21 via 192.202.27.154
     192.202.27.0/25 via 192.202.27.154
     192.202.20.0/22 via 192.202.27.150
     192.202.24.0/23 via 192.202.27.150
     192.202.27.128/28 via 192.202.27.150
     192.202.27.168/30 via 192.202.27.150
     192.202.26.0/24 via 192.202.27.150
     192.202.16.0/22 via 192.202.27.150
     ```
  
- BLUENO (sebagai Client)
     Mengatur IP pada Configuration Blueno yang mengarah ke FOOSHA

     <img width="700" alt="BLUENO ke FOOSHA" src="https://user-images.githubusercontent.com/66562311/143671395-77571aaf-872c-493b-8240-79686c5227ad.PNG">
  
- WATER7 (sebagai Router)
     Mengatur IP pada Configuration WATER7 yang mengarah ke FOOSHA

     <img width="960" alt="WATER7 ke FOOSHA" src="https://user-images.githubusercontent.com/66562311/143671473-6ac36596-dda1-43f8-88bb-f9a460fda0bd.PNG">

     Mengatur IP pada Configuration WATER7 yang mengarah ke CIPHER

     <img width="960" alt="WATER7 ke CIPHER" src="https://user-images.githubusercontent.com/66562311/143671476-84c836ca-816c-4265-8735-9092fb70e10c.PNG">

     Mengatur IP pada Configuration WATER7 yang mengarah ke PUCCI

     <img width="960" alt="WATER7 ke PUCCI" src="https://user-images.githubusercontent.com/66562311/143671485-c93701a6-4a83-4891-8ecd-abe07b439f5f.PNG">  

     Melakukan routing pada WATER7

     <img width="960" alt="WATER7 routing" src="https://user-images.githubusercontent.com/66562311/143671490-ca753aa4-f37b-4cf8-87fe-b3642044edff.PNG">

     ```
     0.0.0.0/0 via 192.202.27.153
     192.202.0.0/21 via 192.202.27.162
     192.202.27.0/25 via 192.202.27.162 
     ```
  
- CIPHER (sebagai Client)
     Mengatur IP pada Configuration CIPHER yang mengarah ke WATER7

     <img width="700" alt="CHIPER ke WATER7" src="https://user-images.githubusercontent.com/66562311/143672383-4df191ba-9347-4d86-a080-bc6a5de775fb.PNG">

- PUCCI (sebagai Router)
     Mengatur IP pada Configuration PUCCI yang mengarah ke WATER7

     <img width="700" alt="PUCCI ke WATER7" src="https://user-images.githubusercontent.com/66562311/143672444-67a4d3c4-c2fb-4aea-8860-7b1ced9fe473.PNG">

     Mengatur IP pada Configuration PUCCI yang mengarah ke CALMBELT dan COURT YARD

     <img width="700" alt="PUCCI ke CALMBELT dan COURT YARD" src="https://user-images.githubusercontent.com/66562311/143672454-8237f3a1-3e17-45ea-bf41-a7fbda679a71.PNG">

     Mengatur IP pada Configuration PUCCI yang mengarah ke JIPANGU

     <img width="700" alt="PUCCI ke JIPANGU" src="https://user-images.githubusercontent.com/66562311/143672447-a85a83be-361a-44a4-b72b-cecf9da974fb.PNG">

     Meleakukan routing pada PUCCI

     <img width="700" alt="PUCCI routing" src="https://user-images.githubusercontent.com/66562311/143672460-b3ca03f0-e04b-4d3c-a4e4-2857a97158a9.PNG">

     ```
     0.0.0.0/0 via 192.202.27.161
     ```
  
- JIPANGU (sebagai Client)
     Mengatur IP pada Configuration JIPANGU yang mengarah ke PUCCI

     <img width="700" alt="JIPANGU ke PUCCI" src="https://user-images.githubusercontent.com/66562311/143672544-ccb92d32-d63f-4301-bdd9-4fc75f67318f.PNG">
  
- CALMBELT (sebagai Client)
     Mengatur IP pada Configuration CALMBELT yang mengarah ke PUCCI

     <img width="700" alt="CALMBELT ke PUCCI" src="https://user-images.githubusercontent.com/66562311/143672558-83eba4ec-c2ee-4cff-9fb7-bf436d18ab3c.PNG">

- COURT YARD (sebagai Client)
     Mengatur IP pada Configuration COURT YARD yang mengarah ke PUCCI

     <img width="700" alt="COURT YARD ke PUCCI" src="https://user-images.githubusercontent.com/66562311/143672565-ca7180db-2759-4393-bac9-beb7cf3d1ffb.PNG">
  
- GUANHO (sebagai Router)
     Mengatur IP pada Configuration GUANHO yang mengarah ke FOOSHA

     <img width="700" alt="GUANHO ke FOOSHA" src="https://user-images.githubusercontent.com/66562311/143672615-ed6dde6c-0715-44b1-bd20-804b164c316e.PNG">

     Mengatur IP pada Configuration GUANHO yang mengarah ke MAINGATE dana ALABASTA

     <img width="700" alt="GUANHO ke MAINGATE dan ALABASTA" src="https://user-images.githubusercontent.com/66562311/143672624-c5ba6a3a-6d49-4153-9fd0-5c16ce31b098.PNG">

     Mengatur IP pada Configuration GUANHO yang mengarah ke OIIMO

     <img width="700" alt="GUANHO ke OIMO" src="https://user-images.githubusercontent.com/66562311/143672632-ffed6b08-9640-450e-9e18-d5186018040d.PNG">

     Mengatur IP pada Configuration GUANHO yang mengarah ke JABRA

     <img width="700" alt="GUANHO ke JABRA" src="https://user-images.githubusercontent.com/66562311/143672636-39fbd80a-59f6-4f8a-adb9-c983a908ba83.PNG">

     Melakukan routing pada GUANHO

     <img width="700" alt="GUANHO routing" src="https://user-images.githubusercontent.com/66562311/143672640-5733952f-eeee-4019-83db-eca86d9f1cb4.PNG">

      ```
      0.0.0.0/0 via 192.202.27.149
      192.202.27.128/28 via 192.202.24.2
      192.202.27.168/30 via 192.202.27.146
      192.202.26.0/24 via 192.202.27.146
      192.202.16.0/22 via 192.202.27.146

      ```
   
- JABRA (sebagai Client)
     Mengatur IP pada Configuration JABRA yang mengarah ke GUANHO

     <img width="700" alt="JABRA ke GUANHO" src="https://user-images.githubusercontent.com/66562311/143672773-621215ff-3323-4ab6-bb51-9cd951e968e6.PNG">

- MAINGATE (sebagai Client)
     Mengatur IP pada Configuration MAINGATE yang mengarah ke GUANHO

     <img width="700" alt="MAINGATE ke GUANHO" src="https://user-images.githubusercontent.com/66562311/143672803-e20a9156-651d-4d1d-a4cb-d63e2551606e.PNG">

- ALABASTA (sebagai Router)
     Mengatur IP pada Configuration ALABASTA yang mengarah ke GUANHO

     <img width="700" alt="ALABASTA ke GUANHO" src="https://user-images.githubusercontent.com/66562311/143672861-cb9ef2da-24da-4e06-9f05-46001d52ac1d.PNG">

     Mengatur IP pada Configuration ALABASTA yang mengarah ke JORGE

     <img width="700" alt="ALABASTA ke JORGE" src="https://user-images.githubusercontent.com/66562311/143672862-e666d09b-a072-4999-8f0f-b8d62706cbda.PNG">

     Melakukan routing pada ALABASTA

     <img width="700" alt="ALABASTA routing" src="https://user-images.githubusercontent.com/66562311/143672867-fca4c595-6ffc-4f90-86ed-58e13cc527c3.PNG">

     ```
     0.0.0.0/0 via 192.202.24.1
     ```
  
- JORGE
     Mengatur IP pada Configuration JORGE yang mengarah ke ALABASTA

     <img width="700" alt="JORGE ke ALABASTA" src="https://user-images.githubusercontent.com/66562311/143672893-6c36aee3-23e1-4c9b-98e1-c9194610c233.PNG">
  
- OIIMO (sebagai Router)
     Mengatur IP pada Configuration OIIMO yang mengarah ke GUANHO

     <img width="700" alt="OIIMO ke GUANHO" src="https://user-images.githubusercontent.com/66562311/143672968-573da040-f301-4375-869d-32a60d7ae0de.PNG">

     Mengatur IP pada Configuration OIIMO yang mengarah ke FUKUROU

     <img width="700" alt="OIIMO ke FUKUROU" src="https://user-images.githubusercontent.com/66562311/143672964-73e56d4a-a12d-4297-95ea-f62e969770d4.PNG">

     Mengatur IP pada Configuration OIIMO yang mengarah ke SEASTONE dan ENIESLOBBY

     <img width="700" alt="OIIMO ke ENIESLOBBY dan SEASTONE" src="https://user-images.githubusercontent.com/66562311/143672961-1d7158e7-5d3c-4efe-b658-7c4e8905a35d.PNG">

     Melakukkan routing pada OIIMO

     <img width="700" alt="OIIMO routing" src="https://user-images.githubusercontent.com/66562311/143672972-cc86f36a-afc3-46a5-be54-081c403887f4.PNG">

     ```
     0.0.0.0/0 via 192.202.27.145
     192.202.16.0/22 via 192.202.26.2
     ```
  
- FUKUROU (sebagai Server)
     Mengatur IP pada Configuration FUKUROU yang mengarah ke OIIMO

     <img width="700" alt="FUKUROU ke OIIMO" src="https://user-images.githubusercontent.com/66562311/143673008-94296e1f-8a62-41c8-9e0e-e6a3c18c8022.PNG">

- ENIESLOBBY (sebagai Client)
     Mengatur IP pada Configuration ENIESLOBBY yang mengarah ke OIIMO

     <img width="700" alt="ENIESLOBBY ke OIIMO" src="https://user-images.githubusercontent.com/66562311/143673066-72f646ad-5097-4f6d-b3f5-004fa2c0359a.PNG">

- SEASTONE (sebagai Router)
     Mengatur IP pada Configuration SEASTONE yang mengarah ke OIIMO

     <img width="700" alt="SEASTONE ke OIMO" src="https://user-images.githubusercontent.com/66562311/143673106-c994c99b-9640-4c3f-9333-81a00b758645.PNG">

     Mengatur IP pada Configuration SEASTONE yang mengarah ke ELENA

     <img width="700" alt="SEASTONE ke ELENA" src="https://user-images.githubusercontent.com/66562311/143673104-d9a3e1b2-2cd8-48ab-b8d8-4033d8436c18.PNG">

     Melakukan routing pada SEASTONE

     <img width="700" alt="SEASTONE routing" src="https://user-images.githubusercontent.com/66562311/143673108-d523e49e-0116-4584-be35-c47c283ca244.PNG">

     ```
     0.0.0.0/0 via 192.202.26.1
     ```
  
- ELENA (sebagai Client)
     Mengatur IP pada Configuration ELENA yang mengarah ke SEASTONE

     <img width="700" alt="ELENA ke SEASTONE" src="https://user-images.githubusercontent.com/66562311/143673154-35096cde-726e-4253-9df5-387c849d273b.PNG">
  
- DORIKI (sebagai Server)
     Mengatur IP pada Configuration DORIKI yang mengarah ke FOOSHA

     <img width="700" alt="DORIKI ke FOOSHA" src="https://user-images.githubusercontent.com/66562311/143673193-f46e5359-169e-46a7-942d-b5f0d045c7e0.PNG">



## CIDR

![iter1](https://user-images.githubusercontent.com/74223938/143684593-5a92d17c-4128-41f8-9ffd-ade663a6fa59.png)
![iter2](https://user-images.githubusercontent.com/74223938/143684602-b7deee4b-e889-4637-8482-f3517e283cd5.png)
![iter3](https://user-images.githubusercontent.com/74223938/143684607-2b439299-3504-463f-9ead-df625b12b3e8.png)
![iter4](https://user-images.githubusercontent.com/74223938/143684612-200ed1ec-d7e0-4486-88cb-7e2bfa189b6c.png)
![iter5](https://user-images.githubusercontent.com/74223938/143684617-4187bd08-bdd5-4d4e-9eb0-bee949a1048b.png)
![iter6](https://user-images.githubusercontent.com/74223938/143684620-9aeb99f8-9297-4653-8b5a-5901e8af2fff.png)
![treeCIDR](https://user-images.githubusercontent.com/74223938/143684621-18f69efa-e1ab-48f7-9e3e-4e391207063c.jpg)
