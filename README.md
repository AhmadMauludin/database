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

# Operasi pada tabel
### Membuat tabel baru
>
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

### Menampilkan isi tabel
- Menampilkan seluruh isi tabel
```
SELECT * FROM namatabel;
```

- Menampilkan isi tabel dengan kondisi tertentu
```
SELECT * FROM namatable WHERE namakolom = 'nilaifilter';
```

- Menampilkan tabel dengan field tertentu
```
SELECT namafield FROM namatable;
```
atau
```
SELECT namafield1, namafield2 FROM namatable';
```

# Operasi pada field
### Mengubah nama field
```
alter table namatabel change fieldlama fieldbaru typedata(pandangdata);
```
Contoh
```
alter table kitab change namakitab ismulkitab varchar(100);
```

### Menghapus field
```
alter table namatabel drop namafield;
```
Contoh :
```
alter table kitab drop ismulkitab;
 ```
# Operasi pada record 
### Mengisi Record Tabel
```
insert into namatabel value (“isi field1","isi field2”);
```
contoh :
```
insert into kitab value (“122","jawahirul kalamiyah”);
```
jika recordnya lebih dari 1 baris maka bisa menggunakan printah :
```
insert into kitab values
(“122","jawahirul kalamiyah”),
(“123","Tijan Darori”),
(“124","Aqidatul Awam”);
```
_**value**_ harus diganti dengan _**values**_

### Mengubah record Tabel
```
update  namatabel  set  namafield = data baru   where   kondisi;
```
contoh :
```
update  kitab  set  ismulkitab = "Safinah"   where   idkitab = 122;
```
atau :
```
update  kitab  set  ismulkitab = "Safinah", idkitab = 343   where   idkitab = 122;
```

### Menghapus record tabel
```
delete from nama_tabel where kondisi;
```
contoh :
```
delete from kitab where idkitab = 343;
```
### Menghapus seluruh record tabel
```
TRUNCATE TABLE namatabel;
```
