# Jarkom-Modul-4-IT05-2023

Yohannes Hasahatan Tua Alexandro - 5027211022

Arkan Hendri Abdul Ghani Burhan - 5027211026

## Soal
Berikut gambar topologi yang harus dibuat
[gambar topologi]

1. Soal shift dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda.
Keterangan: Bila di CPT menggunakan VLSM, maka di GNS3 menggunakan CIDR atau sebaliknya
2. Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal BERSIFAT BENAR dan DAPAT DIKERJAKAN.
Untuk di GNS3 CLOUD merupakan NAT1 jangan sampai salah agar bisa terkoneksi internet.
3. Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan
4. Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.

## Jawaban
### Metode VLSM Menggunakan CPT
Langkah pertama yaitu membuat tree IP seperti tabel berikut ini

![Screenshot 2023-11-28 235649](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/9a7e761d-7b03-4301-8ce5-1c9bc3c81afa)


Setelah dilakukannya pembuatan tree, maka buatlah perhitungan pembagian IP tersebut seperti gambar berikut ini

|Subnet	  |Rute Subnet	|Jumlah IP  |	Netmask| Network ID | IP Netmask | Broadcast |
|---------|---------|---------|---------|---------|---------|---------|
|A5|Aura-Frieren-Flamme-Fern-Switch4-LaubHills-Switch4-AppetittRegion |1023| /21| 10.66.0.0	| 255.255.248.0	| 10.66.7.255|
|A6|Aura-Frieren-Flamme-Switch5-RohrRoad |1001|	/22| 10.66.8.0 |	255.255.252.0 |	10.66.11.255|
|A13|	Aura-Eisen-LugnerSwitch10-TurkRegion |1001|	/22| 10.66.12.0 |	255.255.252.0	| 10.66.15.255 |
|A18|Aura-Eisen-Linie-Lawine-Heiter-Switch8-Sein-Switch8-RiegelCanyon |512|	/22| 10.66.16.0 | 255.255.252.0 |	10.66.19.255|
|A19|	Aura-Eisen-Linie-Switch11-GranzChannel |255|	/23| 10.66.20.0	 | 255.255.254.0	| 10.66.21.255| 
|A14|	Aura-Eisen-Lugner-Switch9-GrobeForest |251|	/24| 10.66.22.0 |	255.255.255.0	| 10.66.22.255|
|A21|	Aura-Denken-Switch2-RoyalCapital-Switch2-WilleRegion |127|	/24| 10.66.23.0 |	255.255.255.0 |	10.66.23.255|
|A17|	Aura-Eisen-Linie-Lawine-Heiter-Switch7-BredtRegion |31|	/26| 10.66.24.0	| 255.255.255.192 |	10.66.24.63|
|A2|	Aura-Frieren-Switch3LakeKorridor |25|	/27| 10.66.24.64	| 255.255.255.224 |	10.66.24.95|
|A8|	Aura-Frieren-Flamme-Himmel-Switch6-SchwerMountains |6|	/29| 10.66.24.96 |	255.255.255.248 |	10.66.24.103|
|A10|	Aura-Eisen-Switch1-Richter-Switch1-Revolte |3|	/29| 10.66.24.104 |	255.255.255.248 |	10.66.24.111|
|A1|	Aura-Frieren |2|	/30| 10.66.24.112	| 255.255.255.252 |	10.66.24.115|
|A3|	Aura-Frieren-Flamme	|2|	/30| 10.66.24.116	255.255.255.252	10.66.24.119|
|A4|	Aura-Frieren-Flamme-Fern	|2|	/30| 10.66.24.120	255.255.255.252	10.66.24.123|
|A7|	Aura-Frieren-Flamme-Himmel	|2|	/30| 10.66.24.124	255.255.255.252	10.66.24.127|
|A9|	Aura-Eisen	|2|	/30| 10.66.24.128	| 255.255.255.252	| 10.66.24.131|
|A11|	Aura-Eisen-Switch0-Stark	|2|	/30| 10.66.24.132 |	255.255.255.252	| 10.66.24.135|
|A12|	Aura-Eisen-Lugner	|2|	/30| 10.66.24.136 |	255.255.255.252	| 10.66.24.139|
|A15|	Aura-Eisen-Linie	|2|	/30| 10.66.24.140 |	255.255.255.252	| 10.66.24.143|
|A16|	Aura-Eisen-Linie-Lawine	|2|	/30| 10.66.24.144	| 255.255.255.252 |	10.66.24.147|
|A20|	Aura-Denken	|2|	/30| |10.66.24.148 |	255.255.255.252 |	10.66.24.151|

Setelah dilakukannya pembagian IP, maka mulai membuat topologi menggunakan Cisco Packet Tracer (CPT) seperti gambar berikut


[gampar cpt]

Selanjutnya melakukan subneting yang bergantung terhadap subnet yang akan dilalui, dengan contoh subnet A20 antara Aura (Eth 1/0) dan Denken (Fa 0/0) dan Subnet A21 antara Denken (Fa 0/1) dan PC RoyalCapital (Fa 0), seperti gambar berikut:

1. Subnetting pada Aura melalui Eth 1/0 pada Subnet A20

![aura_A20](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/54f99ca5-b32c-4762-9d8c-f056774cd201)


2. Subnetting pada Denken melalui Fa 0/0 pada Subnet A20

![denken_A20](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/bda89194-82c3-42b4-971a-e1d155bbc9a4)


3. Subnetting pada Denken melalui Fa 0/1 pada Subnet A21

![denken_A21](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/159a57f3-6d91-492d-a69f-c8a68cb1c18e)


4. Subnetting pada RoyalCapital melalui Fa 0 pada Subnet A21

![royalCapital_A21](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/30992326-fd9c-4b9b-804b-b2463ddc3e43)



Terkhusus pada Server dan PC, diperlukan konfigurasi tambahan yakni pada tab desktop dan opsi Ip Configuration untuk menambahkan Default Gateway dari IP router yang menyambungkannya yakni Denken melalui Fa 0/1, seperti gambar berikut

![royalCapital_A21](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/381bbae9-6f7f-4d0e-86ce-ed68490b0930)



Kemudian dilakukannya routing  terhadap subnet yang ingin dituju dengan mengisi tab static, dengan contoh routing Aura dan Denken terhadap subnet A21

1. Routing pada Aura menuju Denken (routing maju)

![aura_static](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/5ed29f82-2d6f-4e2d-81ad-21de33203e5b)



2. Routing pada Denken menuju Aura (routing mundur)

![denken_static](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/56d398e4-66cb-41c7-a700-efdb81bb8aea)



Lakukan langkah subneting dan routing untuk seluruhnya sampai setiap PC atau Server dapat melakukan ping sampai ke Aura.

Kemudian untuk melakukan ping dari PC atau server atau bahkan router yang berasal dari percabangan subnet yang berbeda, diperlukan langkah tambahan pada routing maju terhadap subnet percabangan tersebut.

Dengan contoh pada Subnet A3 memiliki 3 percabangan yaitu A4, A6, dan A7. Maka ditambahkan langkah routing maju untuk ketiga subnet tersebut pada subnet A3 yaitu dari Frieren (Eth 1/0) menuju Flamme (Fa 0/0)

1. Routing A4 pada Frieren menuju Flamme

![frieren_A4](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/b4ef3c3a-22a4-47c8-95dd-fcecf2481232)


2. Routing A6 pada Frieren menuju Flamme

![frieren_A6](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/d26e238c-08c8-4d83-816f-537ef50ac690)


3. Routing A7 pada Frieren menuju Flamme

![frieren_A7](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/f0529979-7a08-41ae-9f27-d6cdb63676e4)



Lakukan langkah routing tambahan tersebut untuk setiap subnet yang memiliki percabangan terhadap cabang subnet tersebut. Sehingga, seluruh komponen dapat dilakukan ping meski jaraknya berjauhan, seperti gambar berikut
![testPingPC](https://github.com/yohanneslex/Jarkom-Modul-4-IT05-2023/assets/50076171/b68d6b35-c816-43fe-82e2-52ed83c988f0)


1. LaubHils dengan GrobeForest yang dimana dari ujung kiri atas menuju ujung kanan bawah

2. RiegelCanyon dengan RoyalCapital yang dimana dari ujung kiri bawah menuju ujung kanan atas





### Metode CIDR Menggunakan GNS3
