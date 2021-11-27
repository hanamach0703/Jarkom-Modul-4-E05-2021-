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


  


## CIDR
