[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/8b_y5Av8)
| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
|Helsa Sriprameswari Putri| 5025221154 | Jaringan Komputer (C) |
| JAMALUDDIN | 5025221157 | Jaringan Komputer (C) |

## Task 1

> a. Berapa banyak packet yang terekam pada file pcapng?

> _a. How many packets are recorded in the pcapng file?_

**Answer:**

- Flag

  `JARKOM24{K4mu_K3r3n_Q77SIWHAIVTDCG115XPTYH4GNOQ40D0xL4ughiaufplwsl843xa1q0suaaa3}`

- Filter expression -

  
- Explanation

  `Banyak paket yang terekam pada file pcapng dapat dilihat pada bagian bawah. Akan ada tulisan packets : 1089.`
  ![Screenshot 2024-09-12 172444](https://github.com/user-attachments/assets/18abbf88-3e09-4dc7-9093-e316da372461)


- Output result

![flag1](https://github.com/user-attachments/assets/6ceb6cc9-44b2-48a3-b7b8-d7e42f641f9f)

<br>
<br>

> b. Ada berapa jenis protocol yang terekam pada traffic

> _b. How many types of protocols are recorded in the traffic?_

**Answer:**

- Flag

  `JARKOM24{K4mu_K3r3n_Q77SIWHAIVTDCG115XPTYH4GNOQ40D0xL4ughiaufplwsl843xa1q0suaaa3}`

- Filter expression -
  
- Explanation

  `Jumlah protocol dapat dihitung dari kolom Protocol. Agar memudahkan, sorting dari bawah keatas diklik (klik bagian headear protocols). Scrolling  dilakukan dan ditemukan sebanyak 4 Protocol.`<br>
  ![image](https://github.com/user-attachments/assets/8bff4f99-4f86-4f6e-8bc4-f639f78c3ddb)

- Output result

 ![flag1](https://github.com/user-attachments/assets/6ceb6cc9-44b2-48a3-b7b8-d7e42f641f9f)


<br>
<br>

> c. Sebutkan secara berurutan berdasarkan alfabet menurun dengan koma sebagai separator, contoh: protocol1,protocol2

> _c. List the protocols in descending alphabetical order, separated by commas. Example: protocol1,protocol2_

**Answer:**

- Flag

  `JARKOM24{K4mu_K3r3n_Q77SIWHAIVTDCG115XPTYH4GNOQ40D0xL4ughiaufplwsl843xa1q0suaaa3}`

- Filter expression -
  
- Explanation

  `Setelah dilakukan sorting dan scrolling pada kolom protocol, ditemukan terdapat 4 protocol yaitu HTTP,MDNS,SSDP,TCP (urut alfabet)`

- Output result

 ![flag1](https://github.com/user-attachments/assets/6ceb6cc9-44b2-48a3-b7b8-d7e42f641f9f)



## Task 2

> a. Berapa banyak packet berbasis TCP yang memiliki flag [RST, ACK]

> _a. How many TCP based packets have the flags [RST, ACK]?_

**Answer:**

- Flag

  `JARKOM24{W0w_4nother_Sh0t_JSYWPPMLHAH0mptydywxdokeqtfwnmwmmlrvM4r134926296774967030197}`

- Filter expression

  `tcp.flags == 0x14`
  
- Explanation

  `Untuk mencari flag RST dan ACK menggunakan tcp.flags, ACK berada di bit ke-4 (diperoleh 0001 atau 1 dalam biner). Sedangkan RST berada di bit ke-2 (diperoleh 0100 atau 4 dalam biner). Maka dalam heksadesimal diperoleh 0x14. Dengan filter tcp.flags == 0x14 diperoleh jumlah paket sebesar 411. `<br>
  ![image](https://github.com/user-attachments/assets/755e826a-e3c5-4f8b-8ad5-7da7c3fa501a)

- Output result

![WhatsApp Image 2024-09-13 at 13 23 15_391ec808](https://github.com/user-attachments/assets/2b55ffd9-0108-4860-844e-fe0202647994)


<br>
<br>

> b. How many TCP based packets have only the [SYN] flag?

> _b. How many TCP based packets have only the [SYN] flag?_

**Answer:**

- Flag

  `JARKOM24{W0w_4nother_Sh0t_JSYWPPMLHAH0mptydywxdokeqtfwnmwmmlrvM4r134926296774967030197}`

- Filter expression

  `tcp.flags == 0x02`
  
- Explanation

  `Untuk mencari flag SYN menggunakan tcp.flags, SYN berada di bit ke-1 (diperoleh 0010 atau 2 dalam biner). Maka dalam heksadesimal diperoleh 0x02. Dengan filter tcp.flags == 0x02 diperoleh jumlah paket sebesar 412.` <br>
![image](https://github.com/user-attachments/assets/e0600c6e-8730-490b-92b2-ed08f046269d)

- Output result

 ![WhatsApp Image 2024-09-13 at 13 23 15_391ec808](https://github.com/user-attachments/assets/2b55ffd9-0108-4860-844e-fe0202647994)


<br>
<br>

> c. How many TCP based packets have the ACK flag but do not have SYN or RST?

> _c. How many TCP based packets have the ACK flag but do not have SYN or RST?_

**Answer:**

- Flag

  `JARKOM24{W0w_4nother_Sh0t_JSYWPPMLHAH0mptydywxdokeqtfwnmwmmlrvM4r134926296774967030197}`

- Filter expression

  `tcp.flags & 0x10 != 0 && tcp.flags & 0x02 == 0 && tcp.flags & 0x04 == 0 `
  
- Explanation

  `tcp.flags & 0x10 != 0: Memastikan bahwa flag ACK (nilai hex 0x10) diset.`<br>
  `tcp.flags & 0x02 == 0: Memastikan bahwa flag SYN (nilai hex 0x02) tidak diset.`<br>
  `tcp.flags & 0x04 == 0: Memastikan bahwa flag RST (nilai hex 0x04) tidak diset.`<br>
  Hasilnya diperoleh paket sebanyak 217.`

![image](https://github.com/user-attachments/assets/61f04000-b24b-4b14-ac67-0764871f53a2)

- Output result

![WhatsApp Image 2024-09-13 at 13 23 15_391ec808](https://github.com/user-attachments/assets/2b55ffd9-0108-4860-844e-fe0202647994)

<br>
<br>

## Task 3

> a. Pada port berapa server http terbuka?

> _a. On which port is the HTTP server open?_


**Answer:**

- Flag

  `JARKOM24{Y0u_4r3_4_g00d_4nalyz3r_MCBD9L1ts14uh0ewge411bkigsxczyd}`

- Filter expression

  `http`
  
- Explanation

  `Karena yang digunakan http, maka menggunakan filter "http". Pilih paket dengan info HTTP OK lalu dilihat bagian box bawah TCP dengan src port = 9282.`
  ![Screenshot 2024-09-13 141041](https://github.com/user-attachments/assets/9204fce5-5b8c-45fe-8c22-bf3dd564de9c)


- Output result

  `Maaf lupa dokumentasi flag`

<br>
<br>

> b. Berapa byte file response yang dikirim dari server

> _b. How many bytes of file response are sent from the server?_


**Answer:**

- Flag

  `JARKOM24{Y0u_4r3_4_g00d_4nalyz3r_MCBD9L1ts14uh0ewge411bkigsxczyd}`

- Filter expression

  `http`
  
- Explanation

  `Pada paket  HTTP OK, cek detail bagian box tertera 427 bytes captured.`
  ![image](https://github.com/user-attachments/assets/64fde80f-92ca-44d6-9eb1-62b449c64aff)

- Output result

  `Maaf lupa dokumentasi flag`

<br>
<br>

> c. Berapa jumlah file yang terdapat pada server?

> _c. How many files are there on the server?_


**Answer:**

- Flag

  `JARKOM24{Y0u_4r3_4_g00d_4nalyz3r_MCBD9L1ts14uh0ewge411bkigsxczyd}`
  
- Filter expression

  `http`
  
- Explanation

  `Pada paket HTTP OK klik kanan lalu pilih follow http stream maka akan terbuka file htmlnya. Banyak file dapat dihitung pada bagian body html, yaitu ada 4.`
  ![image](https://github.com/user-attachments/assets/f7519f95-7a1d-4dfa-a373-4ad7a756998b)

- Output result

  `Maaf lupa dokumentasi flag`

<br>
<br>

> d. Sebutkan nama file secara berurutan berdasarkan alfabet menurun dengan koma sebagai separator, contoh: file1,file2

> _d. List the filenames in descending alphabetical order, separated by commas. Example: file1,file2_


**Answer:**

- Flag

  `JARKOM24{Y0u_4r3_4_g00d_4nalyz3r_MCBD9L1ts14uh0ewge411bkigsxczyd}`

- Filter expression

  `http`
  
- Explanation

  `Pada paket HTTP OK klik kanan lalu pilih follow http stream maka akan terbuka file htmlnya. Banyak file dapat dihitung pada bagian body html, yaitu ada 4. Filenya adalah file.pdf,hello.html,lion.jpg,present.pptx (diurutkan alfabet)`

- Output result

  `Maaf lupa dokumentasi flag`

<br>
<br>

## Task 4

> Protokol apa yang paling banyak terdapat di file hasil capture traffic?

> _Which protocol is the most frequent in the traffic capture file?_


**Answer:**

- Flag

  `JARKOM24{M4ster_4n4lyzer_07390t1k1PXHUGKETINR41sk4dq2cg8ay}`

- Filter expression

  `ftp`
  
- Explanation

  `Saat melihat list paket dan melakukan scroll down, ditemukan seluruh protocol yang digunakan pada seluruh paket adalah FTP.`
  ![image](https://github.com/user-attachments/assets/21265a9e-3e32-491b-a9da-14d6cdd157bd)


- Output result

  ![WhatsApp Image 2024-09-13 at 14 47 51_1564842f](https://github.com/user-attachments/assets/a5b58833-d280-4caa-9e3d-1c9c8c87b442)

<br>
<br>

## Task 5

> Berdasarkan hasil bruteforce, apa user yang tepat dari hasil bruteforce?

> _Based on the brute force results, what is the correct username?_


**Answer:**

- Flag

  `JARKOM24{He_1s_g3d4g3d1g3d4g3d40_HJVYUDBVBMECDBBTOAQPMunskyzfupnnotnst453087850513}`

- Filter expression

  `ftp contains "USER"`
  
- Explanation

  `Untuk  mencari user digunakan filter "ftp contains user" karena paket menggunakan protocol FTP dan untuk mencari suatu kata (USER) kita menambahkan "contains USER". Setelah list paket muncul, bisa dilakukan brute force. Namun, saya menemukan satu paket yang janggal dengan 88 Request (karena paket lain 70-an requestnya). Dari paket tersebut ditemukan usernya adalah gedagedigedagedao. `
  ![image](https://github.com/user-attachments/assets/812cc064-2b08-430d-94ff-6d4476333f44)


- Output result

 ![WhatsApp Image 2024-09-13 at 13 55 02_d9d58d6c](https://github.com/user-attachments/assets/21f39035-98e7-4fec-becc-55fdbbda9d8e)


<br>
<br>

## Task 6

> Apa password yang tepat?

> _What is the correct password?_


**Answer:**

- Flag

  `JARKOM24{h1s_fr1end_1s_g3d4g3d1g3d4g3d03_N66VC0DSLKyksnUmmhbzfyypvgB4Sur1ACUXXCGPCK}`

- Filter expression

  `ftp.request.command == "PASS"`
  
- Explanation

  `Pertama saya memfilter menggunakan ftp.request.command == "PASS", kemudian saya menfollow tcp stream dan mengecek apakah login success atau incorrect`
  ![image](https://github.com/user-attachments/assets/11eed696-6b6c-43e5-ad3c-9729486bd511)


- Output result

  ![no6](https://github.com/user-attachments/assets/c653cde2-ea88-4e79-9ac4-4e469ec406f4)


<br>
<br>

## Task 7

> Pada port berapa telnet yang bisa diakses?

> _On which port is Telnet accessible?_


**Answer:**

- Flag

  `JARKOM24{Gr34t_Sn1ff3r_REBY4yksnUmialqusebkhT3t0twUqUEJud0m}`

- Filter expression

  `tcp contains "telnet"`
  
- Explanation

  `Pada saat saya mencoba memfollow tcp stream tersebut ternyata user sedang berusaha mengakses telnet`

  ![image](https://github.com/user-attachments/assets/099d6dab-9157-433f-a38d-ca81cbc3a53b)


- Output result

  `Mohon maaf saya lupa untuk menscreenshoot pada saat saya sukses memasukkan jawaban di netcat `

<br>
<br>

## Task 8

> Ada berapa file di dalam server?

> _How many files are on the server?_


**Answer:**

- Flag

  `JARKOM24{P4ck3t_4n4lyz3r_pu4OXptNoL3112vatxbyrsfjS1SXLBXFPBUJQ}`

- Filter expression

  `tcp contains "telnet"`
  
- Explanation

  `kemudian saya memfollow tcp stream, lalu pada akhir text saya menemukan file nya pada saat user mengaktifkan command ls`

  ![image](https://github.com/user-attachments/assets/28206b7b-ffa1-48f6-99b0-749b1f598f10)




- Output result

  `Mohon maaf saya lupa untuk menscreenshoot pada saat saya sukses memasukkan jawaban di netcat`

<br>
<br>

## Task 9 ( REVISI )

> Apa nama file yang dieksekusi oleh user?

> _What is the name of the file executed by the user?_


**Answer:**

- Flag

  `Tidak ada karena revisi`

- Filter expression

  `tcp contains "telnet"`
  
- Explanation

  `Disini saya mencari di telnet dengan menggunakan filter tcp contains "telnet". Kemudian saya memfollow tcp stream, setelah itu mencari file yang di eksekusi oleh user.`
  ![image](https://github.com/user-attachments/assets/8352959e-2a3c-4550-929f-27fe23032880)

  <br>

  `Kemudian saya mencari user mengetikkan "./" karena pada dasarnya file yang dieksekusi pada terminal linux biasanya menggunakan command "./".`

  ![image](https://github.com/user-attachments/assets/f25c1db9-e85b-48f1-b00f-c7bebfe337a2)

  <br>
  
  `Setelah itu saya mendapatkan jawabannya yaitu file yang di eksekusi adalah echo, hal ini juga terlihat pada saat user mengeksekusi command ls pada terminal linux, disitu terdapat file bernama "echo" `

  ![image](https://github.com/user-attachments/assets/ac3d9b12-6052-43da-ab88-14a36913f97e)


- Output result

  `Tidak ada karena ini adalah revisi`

<br>
<br>

## Task 10

> Apa output dari file dalam bentuk base64 decode?

> _What is the output of the file in base64-decoded form?_


**Answer:**

- Flag

  `JARKOM24{tH4ts_1t_w3ll_d0n3_32411984101337dz02ycxxq61231421421VQ94DS9Z3AEOZ63}`

- Filter expression

  `tcp contains "telnet"`
  
- Explanation

  `saya menggunakan filter tersebut karena setau saya telnet memungkinkan untuk berkomunikasi jadi mungkin saja file dengan base64 berada disana, kemudian saya mencari satu satu dengan memfollow tcp stream, setelah itu saya menemukan base64 nya. Selanjutnya saya mendecode base64 menggunakan terminal linux, yaitu dengan | base64 -d`

  ![image](https://github.com/user-attachments/assets/79996523-124b-42b2-b52f-f5db7a33135a)


- Output result

  ![Screenshot 2024-09-11 212452](https://github.com/user-attachments/assets/5600c448-ccc4-4848-b74c-90c74f32064b)

<br>
<br>

## Summary

Overall, beberapa soal dapat bisa dikerjakan dengan baik menggunakan wireshark. Kami juga bisa memahami wireshark filtering serta packet analysis dengan baik.

## Problems

Kami masih belum bisa menyelesaikan soal no 9 pada saat praktikum serta ada kendala jaringan di awal - awal. Beberapa flags juga tidak sempat didokumentasikan.
