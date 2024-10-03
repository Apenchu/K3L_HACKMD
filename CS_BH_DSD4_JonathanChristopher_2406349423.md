# Case Study - Gerbang Logika Kompleks

```
Nama  : Jonathan Christopher 
NPM   : 2406349423
```

## Ikuti skenario di bawah ini! (50 poin)

sori_tutam_susah adalah nama kode seorang hacker nakal yang memiliki akses ke status online/offline dari 4 korbannya (diberi label A, B, C, dan D). Dia ingin membangun circuit LED khusus yang akan menyala jika **MINIMAL SATU** dari kondisi berikut terpenuhi:
- D online.
- A dan B keduanya offline, tetapi setidaknya satu orang lainnya online.
- Tepat 3 orang online.

Bantu hacker tersebut merancang sirkuit menggunakan gerbang kompleks, khususnya XOR dan NAND (tanpa menggunakan NOR).

### Truth Table
|  A  |  B  |  C  |  D  | Output |
|-----|-----|-----|-----|--------|
|  0  |  0  |  0  |  0  |   0    |
|  0  |  0  |  0  |  1  |   1    |
|  0  |  0  |  1  |  0  |   1    |
|  0  |  0  |  1  |  1  |   1    |
|  0  |  1  |  0  |  0  |   0    |
|  0  |  1  |  0  |  1  |   1    |
|  0  |  1  |  1  |  0  |   0    |
|  0  |  1  |  1  |  1  |   1    |
|  1  |  0  |  0  |  0  |   0    |
|  1  |  0  |  0  |  1  |   1    |
|  1  |  0  |  1  |  0  |   0    |
|  1  |  0  |  1  |  1  |   1    |
|  1  |  1  |  0  |  0  |   0    |
|  1  |  1  |  0  |  1  |   1    |
|  1  |  1  |  1  |  0  |   1    |
|  1  |  1  |  1  |  1  |   1    |


### Karnaugh Map 

| AB\CD | 00  | 01  | 11  | 10  |
|-------|-----|-----|-----|-----|
| **00**|  0  |  1  |  1  |  1  |
| **01**|  0  |  1  |  1  |  0  |
| **11**|  0  |  1  |  1  |  1  |
| **10**|  0  |  1  |  1  |  0  |

![image](https://hackmd.io/_uploads/H18D64qA0.png)



### Persamaan Boolean
f(A,B,C,D)= D + ABC + A'B'C
f(A,B,C,D)= D + C(AB+A'B')
f(A,B,C,D)= D + C(A⊕B)'

### Menggunakan persamaan boolean, bangun rangkaian fisik dan ambil foto semua kombinasi yang MENYALAKAN LED!

Rangkaian fisik tidak berhasil sehingga menggunakan Tinkercad.
![WhatsApp Image 2024-10-02 at 20.43.39_b7063f06](https://hackmd.io/_uploads/Hyjey05RC.jpg)
![image](https://hackmd.io/_uploads/Hk-g10qRA.png)
https://www.tinkercad.com/things/hWU53figxCk-csbhdsd4jonathanchristopher2406349423


|  A  |  B  |  C  |  D  | Output |
|-----|-----|-----|-----|--------|
|  0  |  0  |  0  |  1  |![image](https://hackmd.io/_uploads/HJn2k0cCR.png)|
|  0  |  0  |  1  |  0  |![image](https://hackmd.io/_uploads/r1LaJR9C0.png)|
|  0  |  0  |  1  |  1  |![image](https://hackmd.io/_uploads/SykAyA5AA.png)|
|  0  |  1  |  0  |  1  |![image](https://hackmd.io/_uploads/B1uAyC5CC.png)|
|  0  |  1  |  1  |  1  |![image](https://hackmd.io/_uploads/HJyke09C0.png)|
|  1  |  0  |  0  |  1  |![image](https://hackmd.io/_uploads/H1wJlC9C0.png)|
|  1  |  0  |  1  |  1  |![image](https://hackmd.io/_uploads/rkyllR5CR.png)|
|  1  |  1  |  0  |  1  |![image](https://hackmd.io/_uploads/ryDxl0qCR.png)|
|  1  |  1  |  1  |  0  |![image](https://hackmd.io/_uploads/ryJZgA90R.png)|
|  1  |  1  |  1  |  1  |![image](https://hackmd.io/_uploads/HkvWx090C.png)|

---

## Teori (50 poin)

### 1. Jika kamu memiliki variabel X, sebuah gerbang NOT, dan sebuah gerbang XOR, apa yang harus dilakukan agar gerbang XOR selalu mengeluarkan output 1 dari input variabel X? (10 poin)

Agar gerbang XOR selalu mengeluarkan output 1, maka variabel X ada yang langsung ke gerbang XOR dan ada yang melewati gerbang NOT terlebih dahulu lalu ke gerbang XOR. Ketika X itu 0, inverted X akan menyala di gerbang XOR. Ketika X itu 1, inverted X akan menjadi 0 dan tetap menyala di gerbang XOR. X dan X' tidak akan sama dan hanya bernilai 1 dari salah satunya.
|  A  |  A' |  XOR  |
|-----|-----|-------|
|  0  |  1  |   1   |
|  1  |  0  |   1   |

### 2. Menggunakan Boolean equation, jelaskan bagaimana gerbang NAND bisa ekuivalen dengan gerbang NOT! (10 poin)

Gerbang NAND bisa ekuivalen dengan gerbang NOT karena apabila kedua input atau variable yang sama melewati gerbang NAND, maka hasil input tersebut menjadi terbalik atau inverted. Contoh, input X dipasang pada kedua pin input NAND. Ketika X itu bernilai 1, kedua input akan bernilai 1 dan hasilnya akan menjadi 0. Sebaliknya, ketika X bernilai 0, kedua input akan bernilai 0, dan hasilnya menjadi 1.

### 3. Gambarlah gerbang XNOR menggunakan hanya gerbang NOR! (10 poin)

![image](https://hackmd.io/_uploads/HyxvVTcqAC.png)

### 4. Berikan analisis dan kesimpulan untuk case study ini. Analisis harus dalam bentuk paragraf, dan kesimpulan harus disajikan dalam bentuk poin-poin! (20 poin)

### Analisis:  
Pada Case Study kali ini kita membuat rangkaian dari hasil fungsi yang diringkas dari 3 pernyataan. Didapatkan fungsi akhir D + C(A⊕B)'. Rangkaian hanya bisa menggunakan IC 7486 (XOR GATE) dan IC 7400 (NAND GATE). Dengan itu, A dan B melewati XOR GATE dan diteruskan ke NAND GATE. NAND bisa digunakan sebagai NOT GATE dengan cara memasang 1 variabel atau 1 hasil pada kedua pin input IC 7400 atau NAND GATE. Dalam kasus ini, D diinvert dengan diteruskan ke 2 pin input IC 7400. Kemudian invert dari D dan invert dari C(A⊕B)' dipasang ke NAND yang berfungsi sebagai OR.

### Kesimpulan:  
- Gerbang NAND bisa digunakan sebagai gerbang NOT
- Gerbang NAND juga merupakan gerbang OR dari kedua variable yang telah diinvert.
- Gerbang XOR memiliki fungsi AB'+A'B atau (A+B)(A'+B') dengan simbol A⊕B. Sebaliknya (XNOR) adalah AB+A'B' dengan simbol A⊙B. Gerbang ini digunakan apabila hanya ingin mengambil 1 input.