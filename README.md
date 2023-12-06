# Jarkom-Modul-4-D07-2023

## Pendahuluan

Repository ini dibentuk untuk menyelesaikan tugas praktikum Jaringan Komputer.

Anggota Kelompok D07:
| Nama | NRP |
| :---: | :---: |
| Danno Denis Dhaifullah | 5025211027 |
| Fihriz Ilham Rabbany | 5025211040 |

## Pembahasan

### Soal
1. Soal shift dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda.
2. Keterangan: Bila di CPT menggunakan VLSM, maka di GNS3 menggunakan CIDR atau sebaliknya
3. Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal BERSIFAT BENAR dan DAPAT DIKERJAKAN.
4. Untuk di GNS3 CLOUD merupakan NAT1 jangan sampai salah agar bisa terkoneksi internet.
5. Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan
6. Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.
7. Gambar topologi yang lebih jelas dapat diakses pada <a href="https://drive.google.com/file/d/1VmJXOyEoWru1tfXISOgoJiPfE1hpbptM/view?usp=sharing">link berikut</a>



Hal yang perlu diperhatikan

1. Gunakan prefix IP sesuai dengan prefix IP masing-masing.
2. Terdapat template spreadsheet untuk mempermudah penilaian, gunakan template tersebut untuk melakukan penghitungan subnetting.
3. Hasil perhitungan subnetting dan pohon pembagian IP serta file .pkt di submit pada link di atas.
4. File yang didemokan adalah file .pkt yang telah disubmi5t
5. Pengurangan nilai akan dilakukan ketika:
   
   a. Melanggar salah satu dari tulisan diatas.

   b. Tidak menggunakan PREFIX ip yang ditetapkan sebelumnya

   c. Hasil perhitungan untuk VLSM / CIDR, berbeda dengan di CPT / GNS3

   d. Pembagian IP kurang efisien

   e. Routing kurang efisien

   f. Tidak bisa menjelaskan cara perhitungan VLSM dan CIDR


### Jawaban

Pertama, kita perlu membuat rute subnet untuk topologi yang telah diberikan.
Untuk itu, kita bisa membagina menjadi seperti berikut:

![Jarkom Modul 4 D07](Pembagian%20IP%20VLSM/Jarkom%20Modul%204%20D07.png)


#### [Pembagian IP](https://docs.google.com/spreadsheets/d/1RY7FPdDOfv3LuHJhLaor01G5I6M8OCQY6VDW5nYtBE8/edit?usp=sharing) VLSM - GNS3
1. VLSM (Variable Length Subnet Masking)

_Variable Length Subnet Masking_ (VLSM) adalah sebuah metode pengalamatan IP yang memungkinkan pengguna untuk menggunakan subnet mask dengan panjang yang bervariasi untuk mengoptimalkan penggunaan alamat IP dalam jaringan. VLSM memungkinkan kita untuk membagi alamat IP secara lebih efisien dengan mengalokasikan blok alamat yang lebih besar untuk subnet yang membutuhkan lebih banyak host dan blok alamat yang lebih kecil untuk subnet yang membutuhkan lebih sedikit host.

Jadi, pada teknik VLSM, subnet mask (netmask) akan diberikan sesuai dengan kebutuhan jumlah alamat IP dari subnet tersebut. Sesuai dengan jumlah alamat ip yang telah kita bagikan.

Langkah 1 - Tentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.

| No | Length | Usable IPs |
|----|--------|------------|
| 0  | /32    | 1          |
| 1  | /31    | NA         |
| 2  | /30    | 2          |
| 3  | /29    | 6          |
| 4  | /28    | 14         |
| 5  | /27    | 30         |
| 6  | /26    | 62         |
| 7  | /25    | 126        |
| 8  | /24    | 254        |
| 9  | /23    | 510        |
| 10 | /22    | 1022       |
| 11 | /21    | 2046       |
| 12 | /20    | 4094       |
| 13 | /19    | 8190       |
| 14 | /18    | 16382      |
| 15 | /17    | 32766      |
| 16 | /16    | 65534      |
| 17 | /15    | 131070     |
| 18 | /14    | 262142     |
| 19 | /13    | 524286     |
| 20 | /12    | 1048574    |
| 21 | /11    | 2097150    |
| 22 | /10    | 4194302    |
| 23 | /09    | 8388606    |
| 24 | /08    | 16777214   |
| 25 | /07    | 33554430   |
| 26 | /06    | 67108862   |

| Nama Subnet | Rute                                     | Jumlah IP | Netmask |
|-------------|------------------------------------------|-----------|---------|
| A1          | Aura-Frieren                             | 2         | /30     |
| A2          | Frieren-Switch3-LakeKorridor             | 25        | /27     |
| A3          | Frieren-Flamme                            | 2         | /30     |
| A4          | Flamme-Fern                               | 2         | /30     |
| A5          | Fern-Switch4-LaubHills-Switch4-AppetitRegion | 1023  | /21     |
| A6          | Flamme-Switch5-RohrRoad                   | 1001      | /22     |
| A7          | Flamme-Himmel                             | 2         | /30     |
| A8          | Himmel-Switch6-SchwerMountains            | 6         | /29     |
| A9          | Aura-Eisen                                | 2         | /30     |
| A10         | Eisen-Switch1-Richter-Revolte             | 3         | /29     |
| A11         | Eisen-Switch0-Stark                       | 2         | /30     |
| A12         | Eisen-Lugner                              | 2         | /30     |
| A13         | Lugner-Switch10-TurkRegion                | 1001      | /22     |
| A14         | Lugner-Switch9-GrobeForest                | 251       | /24     |
| A15         | Eisen-Linie                               | 2         | /30     |
| A16         | Linie-Lawine                              | 2         | /30     |
| A17         | Lawine-Switch7-BredtRegion                | 31        | /26     |
| A18         | Heiter-Switch8-Sein-Switch8-RiegelCanyon  | 512       | /22     |
| A19         | Linie-Switch11-GranzChannel               | 255       | /23     |
| A20         | Aura-Denken                               | 2         | /30     |
| A21         | Denken-Switch2-RoyalCapital-Switch2-WilleRegion | 127 | /24     |
| Total       |                                        | 4255      | /19     |

Kemudian, berdasarkan tabel di bawah, kita bisa menentukan netmask yang cocok untuk panjang netmask yang telah dibentuk

Berdasarkan total IP dan netmask yang dibutuhkan, maka kita butuh menggunakan netmask /19 untuk memberikan pengalamatan IP pada subnet.

Langkah 2 - Subnet besar yang dibentuk memiliki NID 10.25.0.0 dengan netmask /19. Hitung pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon.

![Kalkulasi](Pembagian%20IP%20VLSM/Kalkulasi.png)


Langkah 3 - Lakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada seperti gambar di bawah ini.

![VLSM TREE](Pembagian%20IP%20VLSM/VLSM%20TREE.png)

Dari pohon dari pohon tersebut akan mendapat pembagian IP sebagai berikut.

| Subnet | Network ID    | Netmask           | Broadcast        |
|--------|---------------|-------------------|------------------|
| A1     | 10.25.24.112  | 255.255.255.252   | 10.25.24.115     |
| A2     | 10.25.24.64   | 255.255.255.224   | 10.25.24.95      |
| A3     | 10.25.24.116  | 255.255.255.252   | 10.25.24.119     |
| A4     | 10.25.24.120  | 255.255.255.252   | 10.25.24.123     |
| A5     | 10.25.0.0     | 255.255.248.0     | 10.25.7.255      |
| A6     | 10.25.8.0     | 255.255.252.0     | 10.25.11.255     |
| A7     | 10.25.24.124  | 255.255.255.252   | 10.25.24.127     |
| A8     | 10.25.24.96   | 255.255.255.248   | 10.25.24.103     |
| A9     | 10.25.24.128  | 255.255.255.252   | 10.25.24.131     |
| A10    | 10.25.24.104  | 255.255.255.248   | 10.25.24.111     |
| A11    | 10.25.24.132  | 255.255.255.252   | 10.25.24.135     |
| A12    | 10.25.24.136  | 255.255.255.252   | 10.25.24.139     |
| A13    | 10.25.12.0    | 255.255.252.0     | 10.25.15.255     |
| A14    | 10.25.22.0    | 255.255.255.0     | 10.25.22.255     |
| A15    | 10.25.24.140  | 255.255.255.252   | 10.25.24.143     |
| A16    | 10.25.24.144  | 255.255.255.252   | 10.25.24.147     |
| A17    | 10.25.24.0    | 255.255.255.192   | 10.25.24.63      |
| A18    | 10.25.16.0    | 255.255.252.0     | 10.25.19.255     |
| A19    | 10.25.20.0    | 255.255.254.0     | 10.25.21.255     |
| A20    | 10.25.24.148  | 255.255.255.252   | 10.25.24.151     |
| A21    | 10.25.23.0    | 255.255.255.0     | 10.25.23.255     |


#### Pembagian IP CIDR - CPT

2. CIDR (Classless Inter Domain Routing)

Langkah 1 - Tentukan subnet yang ada dalam topologi dan lakukan labelling netmask terhadap masing-masing subnet. 

Langkah 2 - Gabungkan subnet paling bawah di dalam topologi, subnet paling jauh dari internet. Maka pada topologi yang digunakan kali ini, subnet yang dapat digabungkan adalah A4 dengan A5, subnet A7 dengan A8, subnet A13 dengan A14, dan subnet A17 dengan A18. Subnet yang digabung tersebut akan membentuk sebuah subnet lebih besar dari subnet-subnet kecil yang ada di dalamnya.


Subnet B1 merupakan hasil penggabungan dari subnet A17 dan A18, Subnet B2 merupakan hasil penggabungan dari subnet A4 dan A5,
Subnet B3 merupakan hasil penggabungan dari subnet A7 dan A8,
Subnet B4 merupakan hasil penggabungan dari subnet A13 dan A14.

Pada teknik CIDR subnet gabungan akan memiliki netmask yang 1 tingkat di atas subnet terbesar yang digabungkan. Berdasarkan contoh di atas A17 = /26 A18 = /22, maka jika dilakukan penggabungan akan menjadi subnet B1 dengan netmask /21. Begitu pula dengan subnet seterusnya.

Lalu ulangi langkah tersebut sampai menjadi sebuah subnet besar yang mencakup 1 topologi yang kita miliki.

![Jarkom Modul 4 D07.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07.png)
![Jarkom Modul 4 D07 CIDR V2 - 8.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%208.png)
![Jarkom Modul 4 D07 CIDR V2 - 7.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%207.png)
![Jarkom Modul 4 D07 CIDR V2 - 6.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%206.png)
![Jarkom Modul 4 D07 CIDR V2 - 5.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%205.png)
![Jarkom Modul 4 D07 CIDR V2 - 4.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%204.png)
![Jarkom Modul 4 D07 CIDR V2 - 3.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%203.png)
![Jarkom Modul 4 D07 CIDR V2 - 2.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%202.png)
![Jarkom Modul 4 D07 CIDR V2 - 1.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2%20-%201.png)
![Jarkom Modul 4 D07 CIDR V2.png](Pembagian%20IP%20CIDR/Jarkom%20Modul%204%20D07%20CIDR%20V2.png)



Langkah 3 - Dari proses penggabungan yang telah dilakukan, didapatkan sebuah subnet besar dengan netmask /14. Kali ini dapat menggunakan NID 10.24.0.0, netmask 255.252.0.0.

Langkah 4 - Hitung pembagian IP dengan pohon berdasarkan penggabungan subnet yang telah dilakukan.

![CIDR TREE](Pembagian%20IP%20CIDR/CIDR%20TREE.png)

Langkah 5 - Berdasarkan penghitungan, maka didapatkan pembagian IP sebagai berikut.

| Subnet | Network ID    | Netmask           | Broadcast        |
|--------|---------------|-------------------|------------------|
| A1     | 10.26.128.0   | 255.255.255.252   | 10.26.128.3     |
| A2     | 10.26.64.0    | 255.255.255.224   | 10.26.64.31     |
| A3     | 10.26.32.0    | 255.255.255.252   | 10.26.32.3      |
| A4     | 10.26.8.0     | 255.255.255.252   | 10.26.8.3       |
| A5     | 10.26.0.0     | 255.255.248.0     | 10.26.7.255     |
| A6     | 10.26.16.0    | 255.255.252.0     | 10.26.19.255    |
| A7     | 10.26.20.8    | 255.255.255.252   | 10.26.20.11     |
| A8     | 10.26.20.0    | 255.255.255.248   | 10.26.20.7      |
| A9     | 10.25.0.0     | 255.255.255.252   | 10.25.0.3       |
| A10    | 10.24.64.0    | 255.255.255.248   | 10.24.64.7      |
| A11    | 10.24.144.0   | 255.255.255.252   | 10.24.144.3     |
| A12    | 10.24.136.0   | 255.255.255.252   | 10.24.136.3     |
| A13    | 10.24.128.0   | 255.255.252.0     | 10.24.131.255   |
| A14    | 10.24.132.0   | 255.255.255.0     | 10.24.132.255   |
| A15    | 10.24.32.0    | 255.255.255.252   | 10.24.32.3      |
| A16    | 10.24.8.0     | 255.255.255.252   | 10.24.8.3       |
| A17    | 10.24.4.0     | 255.255.255.192   | 10.24.4.63      |
| A18    | 10.24.0.0     | 255.255.252.0     | 10.24.3.255     |
| A19    | 10.24.16.0    | 255.255.254.0     | 10.24.17.255    |
| A20    | 10.27.1.0     | 255.255.255.252   | 10.27.1.3      |
| A21    | 10.27.0.0     | 255.255.255.0     | 10.27.0.255    |

#### Konfigurasi IP VLSM

Berdasarkan tree yang telah kami bentuk, selanjutnya kami dapat membagi ip kepada semua node yang ada berdasarkan subneting masing masing. berikut pembagianya:

Aura

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.25.24.113
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.25.24.149
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.25.24.129
	netmask 255.255.255.252
```




Frieren
```
auto eth0
iface eth0 inet static
        address 10.25.24.114
        netmask 255.255.255.252
        gateway 10.25.24.113

auto eth1
iface eth1 inet static
        address 10.25.24.65
        netmask 255.255.255.224

auto eth2
iface eth2 inet static
        address 10.25.24.117
        netmask 255.255.255.252
```

Flamme
```
auto eth0
iface eth0 inet static
        address 10.25.24.118
        netmask 255.255.255.252
        gateway 10.25.24.117

auto eth1
iface eth1 inet static
        address 10.25.24.121
        netmask 255.255.255.252

auto eth2
iface eth2 inet static
        address 10.25.8.1
        netmask 255.255.252.0

auto eth3
iface eth3 inet static
        address 10.25.24.125
        netmask 255.255.255.252
```

Fern
```
auto eth0
iface eth0 inet static
        address 10.25.24.122
        netmask 255.255.255.252
        gateway 10.25.24.121

auto eth1
iface eth1 inet static
        address 10.25.0.1
        netmask 255.255.248.0
```


Himmel
```
auto eth0
iface eth0 inet static
        address 10.25.24.126
        netmask 255.255.255.252
        gateway 10.25.24.125

auto eth1
iface eth1 inet static
        address 10.25.24.97
        netmask 255.255.255.248
```

Eisen
```
auto eth0
iface eth0 inet static
        address 10.25.24.130
        netmask 255.255.255.252
        gateway 10.25.24.129

auto eth1
iface eth1 inet static
        address 10.25.24.105
        netmask 255.255.255.248

auto eth2
iface eth2 inet static
        address 10.25.24.133
        netmask 255.255.255.252

auto eth3
iface eth3 inet static
        address 10.25.24.137
        netmask 255.255.255.252

auto eth4
iface eth4 inet static
        address 10.25.24.141
        netmask 255.255.255.252
```


Lugner
```
auto eth0
iface eth0 inet static
        address 10.25.24.138
        netmask 255.255.255.252
        gateway 10.25.24.137

auto eth1
iface eth1 inet static
        address 10.25.12.1
        netmask 255.255.252.0

auto eth2
iface eth2 inet static
        address 10.25.22.1
        netmask 255.255.255.0
```
Linie
```
auto eth0
iface eth0 inet static
        address 10.25.24.142
        netmask 255.255.255.252
        gateway 10.25.24.141

auto eth1
iface eth1 inet static
        address 10.25.24.145
        netmask 255.255.255.252

auto eth2
iface eth2 inet static
        address 10.25.20.1
        netmask 255.255.254.0
```



Lawine
```
auto eth0
iface eth0 inet static
        address 10.25.24.146
        netmask 255.255.255.252
        gateway 10.25.24.145

auto eth1
iface eth1 inet static
        address 10.25.24.1
        netmask 255.255.255.192
```

Heiter
```
auto eth0
iface eth0 inet static
        address 10.25.24.3
        netmask 255.255.255.192
        gateway 10.25.24.1

auto eth1
iface eth1 inet static
        address 10.25.16.1
        netmask 255.255.252.0
```


Denken
```
auto eth0
iface eth0 inet static
        address 10.25.24.150
        netmask 255.255.255.252
        gateway 10.25.24.149

auto eth1
iface eth1 inet static
        address 10.25.23.1
        netmask 255.255.255.0
```

Sein	
```
auto eth0	
iface eth0 inet static	
         address 10.25.16.2	
         netmask 255.255.252.0	
         gateway 10.25.16.1	
```

RiegelCanyon	
```
auto eth0	
iface eth0 inet static	
         address 10.25.16.3	
         netmask 255.255.252.0	
         gateway 10.25.16.1	
```

GranzChannel	
```
auto eth0	
iface eth0 inet static	
         address 10.25.20.2	
         netmask 255.255.254.0	
         gateway 10.25.20.1	
```

LaubHils
```	
auto eth0	
iface eth0 inet static	
         address 10.25.0.2	
         netmask 255.255.248.0	
         gateway 10.25.0.1	
```
	
	
BredtRegion	
```	
auto eth0	
iface eth0 inet static	
         address 10.25.24.2	
         netmask 255.255.255.192	
         gateway 10.25.24.1	
```	
		
LakeKorridor	
```
auto eth0	
iface eth0 inet static	
         address 10.25.24.66	
         netmask 255.255.255.224	
         gateway 10.25.24.65	
```

Turk Region	
```	
auto eth0	
iface eth0 inet static	
         address 10.25.12.2	
         netmask 255.255.255.252	
         gateway 10.25.12.1	
```	

Grobe Forest	
```
auto eth0	
iface eth0 inet static	
         address 10.25.22.2	
         netmask 255.255.255.252	
         gateway 10.25.22.1	
```	

Appetit Region	
```
auto eth0	
iface eth0 inet static	
         address 10.25.0.3	
         netmask 255.255.248.0	
         gateway 10.25.0.1	
```	
	
RohrRoad	
```
auto eth0	
iface eth0 inet static	
         address 10.25.8.2	
         netmask 255.255.252.0	
         gateway 10.25.8.1	
```

RoyalCaptain	
```
auto eth0	
iface eth0 inet static	
         address 10.25.23.2	
         netmask 255.255.255.0	
         gateway 10.25.23.1	
```	
	
	
WilleRegion	
```
auto eth0	
iface eth0 inet static	
         address 10.25.23.3	
         netmask 255.255.255.0	
         gateway 10.25.23.1	
```	

Richter	
```
auto eth0	
iface eth0 inet static	
         address 10.25.24.106	
         netmask 255.255.255.252	
         gateway 10.25.24.105	
```	
	
Revolte	
```
auto eth0	
iface eth0 inet static	
         address 10.25.24.107	
         netmask 255.255.255.252	
         gateway 10.25.24.105	
```	


Stark	
```
auto eth0	
iface eth0 inet static	
         address 10.25.24.134	
         netmask 255.255.255.252	
         gateway 10.25.24.133	
```	

SchwerMountains	
```
auto eth0	
iface eth0 inet static	
         address 10.25.24.98	
         netmask 255.255.255.248	
         gateway 10.25.24.97	
```	

Semua pembagian IP pada router juga berlaku sesuai dengan pembagian IP yang sudah dilakukan perhitungan sebelumnya. Pengaturan config juga dilakukan pada _edge device_ atau ujung dari setiap topologi entah itu _client_ maupun server. berikut contoh node lanjutan client dari denken.

Konfigurasi dilakukan pada semua node yang ada dari router sampai _client_ maupun server, semua dilakukan dengan pembagian IP yang telah dilakukan.

#### Konfigurasi IP CIDR
Aura
![Screenshot 2023-12-06 142216.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142216.png)
![Screenshot 2023-12-06 142401.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142401.png)
![Screenshot 2023-12-06 142424.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142424.png)

Frieren
![Screenshot 2023-12-06 142448.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142448.png)
![Screenshot 2023-12-06 142519.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142519.png)
![Screenshot 2023-12-06 142536.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142536.png)

Flamme
![Screenshot 2023-12-06 142625.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142625.png)
![Screenshot 2023-12-06 142713.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142713.png)
![Screenshot 2023-12-06 142804.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142804.png)
![Screenshot 2023-12-06 142816.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142816.png)

Fern
![Screenshot 2023-12-06 142842.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142842.png)
![Screenshot 2023-12-06 142905.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142905.png)

Himmel
![Screenshot 2023-12-06 142933.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142933.png)
![Screenshot 2023-12-06 142954.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20142954.png)

Eisen
![Screenshot 2023-12-06 143300.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143300.png)
![Screenshot 2023-12-06 143314.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143314.png)
![Screenshot 2023-12-06 143328.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143328.png)
![Screenshot 2023-12-06 143341.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143341.png)
![Screenshot 2023-12-06 143354.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143354.png)

Linie
![Screenshot 2023-12-06 143437.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143437.png)
![Screenshot 2023-12-06 143458.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143458.png)
![Screenshot 2023-12-06 143511.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143511.png)

Lawine
![Screenshot 2023-12-06 143534.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143534.png)
![Screenshot 2023-12-06 143548.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143548.png)

Heiter
![Screenshot 2023-12-06 143605.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143605.png)
![Screenshot 2023-12-06 143620.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143620.png)

Lugner
![Screenshot 2023-12-06 143652.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143652.png)
![Screenshot 2023-12-06 143703.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143703.png)
![Screenshot 2023-12-06 143717.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143717.png)

Denken
![Screenshot 2023-12-06 143748.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143748.png)
![Screenshot 2023-12-06 143802.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143802.png)

LakeKorridor
![Screenshot 2023-12-06 143826.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143826.png)

LaubHills
![Screenshot 2023-12-06 143849.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143849.png)

AppetitRegion
![Screenshot 2023-12-06 143908.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143908.png)

RohrRoad
![Screenshot 2023-12-06 143937.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20143937.png)

SchwerMountains
![Screenshot 2023-12-06 144000.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144000.png)

BredtRegion
![Screenshot 2023-12-06 144048.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144048.png)

Sein
![Screenshot 2023-12-06 144205.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144205.png)

RiegelCanyon
![Screenshot 2023-12-06 144223.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144223.png)

GranzChannel
![Screenshot 2023-12-06 144328.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144328.png)

GrobeForest 
![Screenshot 2023-12-06 144351.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144351.png)

TurkRegion
![Screenshot 2023-12-06 144518.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144518.png)

Richter
![Screenshot 2023-12-06 144617.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144617.png)

Revolte
![Screenshot 2023-12-06 144707.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144707.png)

Stark
![Screenshot 2023-12-06 144730.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144730.png)

WilleRegion
![Screenshot 2023-12-06 144803.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144803.png)

RoyalCapital
![Screenshot 2023-12-06 144821.png](Konfigurasi%20IP%20CIDR/Screenshot%202023-12-06%20144821.png)

#### Routing GNS3

Sama halnya seperti VLSM yang dilakukan routing pada Cisco packet tracker, pada GNS3 CRID juga harus dilakukan routing untuk menentukan route atau rute mana yang saling terhubung satu sama yang lain. Routing dilakukan pada setiap router, router akan meneruskan permintaan yang dilakukan pada _client_ apabila ingin melakukan `ping` pada subnet yang jauh, maka fungsi router itu sendiri untuk menghubungkan jaringan atau subnet yang telah dibuat agar dapat menjangkau node yang jauh, mengetahui rute yang ingin ditempuh sehingga dapat sampai pada node yang diinginkan dengan cepat dan tepat.

Berikut merupakan langkah-langkah sederhana yang dapat dilakukan pada router untuk melakukan routing pada GNS3 secara manual dengan memasukkan command berikut kedalam terminal router.

```
route add -net <NID subnet> netmask <netmask> gw <IP gateway>
```

- **NID** merupakan NID dari pembagian IP sebelumnya
- **netmask** merupakan perhitungan netmask yang didapat dari NID
- **IP gateway** merupakan jalur yang harus ditempuh untuk meneruskan request yang dilakukan

Setelah melakukan _command_ tersebut dapat dilakukan pengecekan dengan menggunakan _command_ sebagai berikut:

```
route -n
```

Aura
``` 
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.25.0.0/16
route add -net 10.25.24.64 netmask 255.255.255.224 gw 10.25.24.114
route add -net 10.25.24.116 netmask 255.255.255.252 gw 10.25.24.114
route add -net 10.25.24.120 netmask 255.255.255.252 gw 10.25.24.114
route add -net 10.25.0.0 netmask 255.255.248.0 gw 10.25.24.114
route add -net 10.25.8.0 netmask 255.255.252.0 gw 10.25.24.114
route add -net 10.25.24.124 netmask 255.255.255.252 gw 10.25.24.114
route add -net 10.25.24.96 netmask 255.255.255.248 gw 10.25.24.114
route add -net 10.25.24.104 netmask 255.255.255.248 gw 10.25.24.130
route add -net 10.25.24.132 netmask 255.255.255.252 gw 10.25.24.130
route add -net 10.25.24.136 netmask 255.255.255.252 gw 10.25.24.130
route add -net 10.25.12.0 netmask 255.255.252.0 gw 10.25.24.130
route add -net 10.25.22.0 netmask 255.255.255.0 gw 10.25.24.130
route add -net 10.25.24.140 netmask 255.255.255.252 gw 10.25.24.130
route add -net 10.25.24.144 netmask 255.255.255.252 gw 10.25.24.130
route add -net 10.25.24.0 netmask 255.255.255.192 gw 10.25.24.130
route add -net 10.25.16.0 netmask 255.255.252.0 gw 10.25.24.130
route add -net 10.25.20.0 netmask 255.255.254.0 gw 10.25.24.130
route add -net 10.25.23.0 netmask 255.255.255.0 gw 10.25.24.150
```

Frieren
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.113
route add -net 10.25.24.120 netmask 255.255.255.252 gw 10.25.24.118
route add -net 10.25.0.0 netmask 255.255.248.0 gw 10.25.24.118
route add -net 10.25.8.0 netmask 255.255.252.0 gw 10.25.24.118
route add -net 10.25.24.124 netmask 255.255.255.252 gw 10.25.24.118
route add -net 10.25.24.96 netmask 255.255.255.248 gw 10.25.24.118
```

Flamme
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw  10.25.24.117
route add -net 10.25.0.0 netmask 255.255.248.0 gw 10.25.24.122
route add -net 10.25.24.96 netmask 255.255.255.248 gw 10.25.24.126
```

Fern
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.121
```

Himmel
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.125
```

Eisen
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.129
route add -net 10.25.12.0 netmask 255.255.252.0 gw 10.25.24.138
route add -net 10.25.22.0 netmask 255.255.255.0 gw 10.25.24.138
route add -net 10.25.24.144 netmask 255.255.255.252 gw 10.25.24.142
route add -net 10.25.24.0 netmask 255.255.255.192 gw 10.25.24.142
route add -net 10.25.16.0 netmask 255.255.252.0 gw 10.25.24.142
route add -net 10.25.20.0 netmask 255.255.254.0 gw 10.25.24.142
```

Lugner
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.137
```

Linie
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.141
route add -net 10.25.24.0 netmask 255.255.255.192 gw 10.25.24.146
route add -net 10.25.16.0 netmask 255.255.252.0 gw 10.25.24.146
```

Lawine
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.145
route add -net 10.25.16.0 netmask 255.255.252.0 gw 10.25.24.3
```

Heiter
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.1
```

Denken
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.25.24.149
```

#### Routing CPT
Aura
```
ip route 10.26.64.0 255.255.255.224 10.26.128.2
ip route 10.26.32.0 255.255.255.252 10.26.128.2
ip route 10.26.8.0 255.255.255.252 10.26.128.2
ip route 10.26.0.0 255.255.248.0 10.26.128.2
ip route 10.26.16.0 255.255.252.0 10.26.128.2
ip route 10.26.20.8 255.255.255.252 10.26.128.2
ip route 10.26.20.0 255.255.255.248 10.26.128.2
ip route 10.24.64.0 255.255.255.248 10.25.0.2
ip route 10.24.144.0 255.255.255.252 10.25.0.2
ip route 10.24.136.0 255.255.255.252 10.25.0.2
ip route 10.24.128.0 255.255.252.0 10.25.0.2
ip route 10.24.132.0 255.255.255.0 10.25.0.2
ip route 10.24.32.0 255.255.255.252 10.25.0.2
ip route 10.24.8.0 255.255.255.252 10.25.0.2
ip route 10.24.4.0 255.255.255.192 10.25.0.2
ip route 10.24.0.0 255.255.252.0 10.25.0.2
ip route 10.24.16.0 255.255.254.0 10.25.0.2
ip route 10.27.0.0 255.255.255.0 10.27.1.2
```

Frieren
```
ip route 0.0.0.0 0.0.0.0 10.26.128.1
ip route 10.26.8.0 255.255.255.252 10.26.32.2
ip route 10.26.0.0 255.255.248.0 10.26.32.2
ip route 10.26.16.0 255.255.252.0 10.26.32.2
ip route 10.26.20.8 255.255.255.252 10.26.32.2
ip route 10.26.20.0 255.255.255.248 10.26.32.2
```

Flamme
```
ip route 0.0.0.0 0.0.0.0 10.26.32.1
ip route 10.26.0.0 255.255.248.0 10.26.8.2
ip route 10.26.20.0 255.255.255.248 10.26.20.10
```

Fern
```
ip route 0.0.0.0 0.0.0.0 10.26.8.1
```

Himmel
```
ip route 0.0.0.0 0.0.0.0 10.26.20.9
```

Eisen
```
ip route 0.0.0.0 0.0.0.0 10.25.0.1
ip route 10.24.128.0 255.255.252.0 10.24.136.2
ip route 10.24.132.0 255.255.255.0 10.24.136.2

ip route 10.24.8.0 255.255.255.252 10.24.32.2
ip route 10.24.4.0 255.255.255.192 10.24.32.2
ip route 10.24.0.0 255.255.252.0 10.24.32.2
ip route 10.24.16.0 255.255.254.0 10.24.32.2
```

Lugner
```
ip route 0.0.0.0 0.0.0.0 10.24.136.1
```

Linie
```
ip route 0.0.0.0 0.0.0.0 10.24.32.1
ip route 10.24.4.0 255.255.255.192 10.24.8.2
ip route 10.24.0.0 255.255.252.0 10.24.8.2
```

Lawine
```
ip route 0.0.0.0 0.0.0.0 10.24.8.1
ip route 10.24.0.0 255.255.252.0 10.24.4.2
```

Heiter
```
ip route 0.0.0.0 0.0.0.0 10.24.4.1
```

Denken
```
ip route 0.0.0.0 0.0.0.0 10.27.1.1
```

#### Testing GNS3
![IP GranzChannel.png](Testing/IP%20GranzChannel.png)
![Ping CPT.png](Testing/Ping%20CPT.png)

#### Testing CPT
![Ping LaubHills GranzChannel.png](Testing/Ping%20LaubHills%20GranzChannel.png)



#### Kendala
Tidak ada kendala yang signifikan dalam pengerjaan soal.

