# Langkah langkah menggunakan my sql
### Persiapan
- install terlebih dahulu **xampp**
- buka **xampp control panel**
- aktifkan **mysql**
- buka cmd, caranya tekan **windows + R** lalu klik **OK**

### Menggunakan CMD
Pertama tama kalian pastikan berada pada direktori / folder yang tepat, yaitu pada direktri **xampp\mysql\bin**
- keluar direktori dengan menggunakan perintah ```cd..```
- masuk / memilih direktori dengan menggunakan perintah ```cd namadirektori```
- maka gunakan perintah berikut ```cd xampp\mysql\bin```
- setelah anda berada pada direktori tersebut, masukan perintah ```mysql -u root -p``` lalu masukkan password

_jika tidak menggunakan password, langsung saja enter_

### Operasi pada database
- ```show databases;``` untuk **Melihat database** yang ada pada direktori tersebut
- ```create database namadatabase;``` untuk **membuat database baru**
- ```drop database namadatabase;``` untuk **menghapus database**
- ```use namadatabase;``` untuk **memilih database**
- ```show tables;``` untuk **melihat tabel** apa saja yang ada pada database tersebut
- ```desc namatabel;``` untuk **melihat struktur tabel**
- ```drop table namatabel;``` untuk **menghapus tabel**

### Operasi pada tabel
**Membuat tabel baru** perintahnya adalah
```
create table namatabel (
  namakolom typedata(panjangdata),
  namakolom typedata(panjangdata)
);
```
contohnya :
```
create table kitab (
    -> idkitab int(3),
    -> namakitab varchar(50)
    -> );
```
kita juga dapat menambahkan script
- ```AUTO_INCREMENT``` untuk **membuat record field integer terisi otomatis**
- ```PRIMARY KEY``` untuk **memilih salahsatu atribut primary key** dari salahsatu field
- ```NOT NULL``` agar **record file harus selalu diisi**

contoh :
```
create table kitab (
  -> idkitab int AUTO_INCREMENT PRIMARY KEY,
  -> namakitab varchar(50) NOT NULL
  -> );
```

**Mengubah nama field**
```
alter table namatabel change fieldlama fieldbaru typedata(pandangdata);
```
