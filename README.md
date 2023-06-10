# Praktikum 5
Nama : Anggita Risqi Nur Clarita

NIM : 312210450

Kelas : TI.22.A.4

Mata Kuliah : Basis Data

Dosen Pengampu : Agung Nugroho, S.Kom., M.Kom.

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|SQL JOIN|[Click Here](#sql-join)|
|2|Soal Praktikum 5|[Click Here](#soal-praktikum-5)|
|3|Script SQL berdasarkan skema data|[Click Here](#buat-script-sql-join-berdasarkan-skema-data-pada-soal-praktikum-5)|
|4|Latihan|[Click Here](#latihan-praktikum-5)|
|5|Laporan Praktikum 5 (PDF)|[Click Here](https://drive.google.com/file/d/1SSZysFZlEJGklNm1fux6kCxSlwxpKvHN/view?usp=drivesdk)|

## SQL JOIN
> ### *JOIN TABLE*
> Operasi Join merupakan operasi yang digunakan untuk menggabungkan dua tabel atau lebih dengan hasil berupa gabungan dari kolom-kolom yang berasal dari tabel-tabel tersebut

> ### *Jenis JOIN*
> 1. **NATURAL JOIN / INNER JOIN** : Digunakan untuk menampilkan baris tabel yang memiliki nilai yang sama pada kolom yang terkait.
>
> 2. **LEFT JOIN** : Digunakan untuk menampilkan semua data pada table A dan sebagian data pada table B yang bersinggungan dengan table A.
>
> 3. **RIGHT JOIN** : Digunakan untuk menampilkan semua data pada table B dan sebagian data pada table A yang bersinggungan dengan table B.
>
> 4. **FULL JOIN / UNION** : Digunakan untuk menampilkan semua data pada table A dan B.
 

## *Soal Praktikum 5*
[Link Soal](https://drive.google.com/file/d/10d1dPyahHFo7fhuF4fwc38ShGaTCAF6n/view?usp=drivesdk)

## Buat Script SQL Join berdasarkan skema data pada soal Praktikum 5!
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/Tabel%20Mahasiswa.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/Tabel%20Dosen%20dan%20MataKuliah.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/Tabel%20JadwalMengajar.png)
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/Tabel%20KRS.png)

### *Script SQL berdasarkan Tabel Mahasiswa*
```sql
CREATE TABLE Mahasiswa(
nim VARCHAR(10) NOT NULL PRIMARY KEY,
nama VARCHAR(100) NOT NULL,
jk ENUM('L', 'P') NOT NULL,
tgl_lahir DATE NOT NULL,
jalan VARCHAR(100) DEFAULT NULL,
Kota VARCHAR(50) NOT NULL,
kodepos VARCHAR(20) DEFAULT NULL,
no_hp VARCHAR(20) DEFAULT NULL,
kd_ds VARCHAR(10) DEFAULT NULL
);

INSERT INTO Mahasiswa (nim, nama, jk, tgl_lahir, jalan, kota, kodepos, no_hp, kd_ds) VALUES
('1812345', 'Ari Santoso', 'L', '1979-10-11', NULL, 'Bekasi', NULL, NULL, 'DS002'),
('1823456', 'Dina Marlina', 'P', '1999-11-20', NULL, 'Cikarang', NULL, NULL, NULL),
('1834567', 'Rahmat Hidayat', 'L', '1999-05-10', NULL, 'Bekasi', NULL, NULL, NULL),
('1845678', 'Jaka Sampurna ', 'L', '1996-10-19', NULL, 'Cikarang', NULL, NULL, NULL),
('1856789', 'Tia Lestari', 'P', '1908-02-15', NULL, 'Karawang', NULL, NULL, NULL),
('1867890', 'Anton Sinaga', 'L', '1988-06-22', NULL, 'Bekasi', NULL, NULL, NULL),
('1912345', 'Listia Nastiti', 'P', '1999-10-23', NULL, 'Jakarta', NULL, NULL, NULL),
('1923456', 'Amira Jarisa', 'P', '1999-01-24', NULL, 'Karawang', NULL, NULL, 'DS004'),
('1934567', 'Laksana Mardito', 'L', '1999-04-14', NULL, 'Cikarang', NULL, NULL, NULL),
('1945678', 'Jura Marsina', 'P', '1999-05-10', NULL, 'Cikarang', NULL, NULL, NULL),
('1956789', 'Dadi Martani', 'L', '1999-08-29', NULL, 'Bekasi', NULL, NULL, 'DS005'),
('1967890', 'Bayu Laksono', 'L', '1999-07-22', NULL, 'Cikarang', NULL, NULL, 'DS004');
SELECT * FROM Mahasiswa;
```

### *Output Tabel Mahasiswa*
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/1.png)


### *Script SQL berdasarkan Tabel Dosen*
```sql
CREATE TABLE Dosen(
kd_ds VARCHAR(10) NOT NULL PRIMARY KEY,
nama VARCHAR(100) NOT NULL
);

INSERT INTO Dosen (kd_ds, nama) VALUES
('DS001', 'Nofal Arianto'),
('DS002', 'Ario Talib'),
('DS003', 'Ayu Rahmadina'),
('DS004', 'Ratna Kumala'),
('DS005', 'Vika Prasetyo');
SELECT * FROM Dosen;
```

### *Output Tabel Dosen*
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/2.png)

### *Script SQL berdasarkan Tabel Mata Kuliah*
```sql
CREATE TABLE Matakuliah(
kd_mk VARCHAR(10) NOT NULL PRIMARY KEY,
nama VARCHAR(100) NOT NULL,
sks INT NOT NULL
);

INSERT INTO MataKuliah (kd_mk, nama, sks) VALUES
('MK001', 'Algoritma Dan Pemrogaman', '3'),
('MK002', 'Praktikum Algoritma Dan Pemrograman', '1'),
('MK003', 'Teknologi Basis Data', '3'),
('MK004', 'Praktikum Teknologi Basis Data', '1'),
('MK005', 'Pemrograman Dasar', '3'),
('MK006', 'Pemrograman Berorientasi Objek', '3'),
('MK007', 'Struktur Data', '3'),
('MK008', 'Arsitektur Komputer', '2');
SELECT * FROM MataKuliah;
```

### *Output Tabel Mata Kuliah*
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/3.png)


### *Script SQL berdasarkan Tabel Jadwal Mengajar*
```sql
CREATE TABLE JadwalMengajar(
kd_mk VARCHAR(10) NOT NULL,
kd_ds VARCHAR(10) NOT NULL,
hari ENUM('Senin', 'Selasa', 'Rabu', 'Kamis', 'Jumat', 'Sabtu', 'Minggu'),
jam TIME NOT NULL,
ruang VARCHAR(50),
PRIMARY KEY(kd_mk, kd_ds)
);

INSERT INTO JadwalMengajar (kd_mk, kd_ds, hari, jam, ruang) VALUES
('MK001', 'DS002', 'Senin', '10:00:00', '102'),
('MK002', 'DS002', 'Senin', '13:00:00', 'Lab. 01'),
('MK003', 'DS001', 'Selasa', '08:00:00', '201'),
('MK004', 'DS001', 'Rabu', '10:00:00', 'Lab. 02'),
('MK005', 'DS003', 'Selasa', '10:00:00', 'Lab. 01'),
('MK006', 'DS004', 'Kamis', '09:00:00', 'Lab. 03'),
('MK007', 'DS005', 'Rabu', '08:00:00', '102'),
('MK008', 'DS005', 'Kamis', '13:00:00', '201');
SELECT * FROM JadwalMengajar;
```

### *Output Tabel Mata Kuliah*
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/4.png)


### *Script SQL berdasarkan Tabel KRS Mahasiswa*
```sql
CREATE TABLE KRSMahasiswa(
nim VARCHAR(10) NOT NULL,
kd_mk VARCHAR(10) NOT NULL,
kd_ds VARCHAR(10) NOT NULL,
semester VARCHAR(30) NOT NULL,
nilai VARCHAR(50) DEFAULT NULL,
PRIMARY KEY(nim, kd_mk, kd_ds)
);

INSERT INTO KRSMahasiswa (nim, kd_mk, kd_ds, semester, nilai) VALUES
('1823456', 'MK001', 'DS002', '3', NULL),
('1823456', 'MK002', 'DS002', '1', NULL),
('1823456', 'MK003', 'DS001', '3', NULL),
('1823456', 'MK004', 'DS001', '3', NULL),
('1823456', 'MK007', 'DS005', '3', NULL),
('1823456', 'MK008', 'DS005', '3', NULL);
SELECT * FROM KRSMahasiswa;
```

### *Output Tabel Mata Kuliah*
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/5.png)


## Latihan Praktikum 5
![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/Soal.png)

### 1. Lakukan join table Mahasiswa dan Dosen
**Script (Menggunakan INNER JOIN)**

```sql
SELECT Mahasiswa.nim, Mahasiswa.nama, Mahasiswa.jk, Dosen.nama AS "Dosen PA"
FROM Mahasiswa INNER JOIN Dosen ON Dosen.kd_ds = Mahasiswa.kd_ds;
```

**Output**

![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/6.png)

> **Keterangan** : INNER JOIN digunakan untuk mengambil data yang terkait dari dua tabel atau lebih dengan hanya menampilkan baris yang memiliki nilai yang sama pada kolom yang terkait.


**Script (Menggunakan LEFT JOIN)**

```sql
SELECT Mahasiswa.nim, Mahasiswa.nama, Mahasiswa.jk, Dosen.nama AS "Dosen PA"
FROM Mahasiswa LEFT JOIN Dosen ON Dosen.kd_ds = Mahasiswa.kd_ds;
```

**Output**

![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/7.png)

> **Keterangan** : LEFT LOIN digunakan untuk menampilkan semua data pada table Mahasiswa dan sebagian data pada table Dosen yang bersinggungan dengan table Mahasiswa.

### 2. Lakukan join tabel Matakuliah dan Dosen
**Script**

```sql
SELECT Matakuliah.kd_mk, Matakuliah.nama, Matakuliah.sks, Dosen.nama AS "Dosen Pengampu"
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;
```

**Output**

![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/8.png)

> **Keterangan** : JOIN table JadwalMengajar, Dosen, dan MataKuliah (kd_mk, nama, sks, Dosen Pengampu)

### 3. Lakukan join table JadwalMengajar, Dosen, dan MataKuliah
**Script**

```sql
SELECT Matakuliah.kd_mk, Matakuliah.nama, Matakuliah.sks, Dosen.nama AS "Dosen Pengampu", JadwalMengajar.hari, JadwalMengajar.jam, JadwalMengajar.ruang
FROM JadwalMengajar
LEFT JOIN Matakuliah ON JadwalMengajar.kd_mk = Matakuliah.kd_mk
LEFT JOIN Dosen ON JadwalMengajar.kd_ds = Dosen.kd_ds;
```

**Output**

![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/9.png)

> **Keterangan** : JOIN table JadwalMengajar, Dosen, dan MataKuliah (kd_mk, nama, sks, Dosen Pengampu, hari, jam, ruang)

### 4. Lakukan join tabel KRSMahasiswa, Mahasiswa, MataKuliah, dan Dosen
**Script**

```sql
SELECT Mahasiswa.nim, Mahasiswa.nama AS "nama", Dosen.nama AS "Dosen PA", Matakuliah.nama AS "Matakuliah", Matakuliah.sks, Dosen.nama AS "Dosen Pengampu"
FROM KRSMahasiswa
JOIN Mahasiswa ON KRSMahasiswa.nim = Mahasiswa.nim
JOIN Matakuliah ON KRSMahasiswa.kd_mk = Matakuliah.kd_mk
JOIN Dosen ON KRSMahasiswa.kd_ds = Dosen.kd_ds;
```

**Output**

![image](https://github.com/AnggitaRisqiNC/Praktikum-5/blob/main/screenshot/10.png)

> **Keterangan** : JOIN tabel KRSMahasiswa, Mahasiswa, MataKuliah, dan Dosen (Nama mahasiswa dan nim yang tampil sesuai dengan data yang diinput sebelumnya pada tabel KRSMahasiswa)

## Finish