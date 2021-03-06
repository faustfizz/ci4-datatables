![GitHub](https://img.shields.io/github/license/irsyadulibad/ci4-datatables)
![GitHub repo size](https://img.shields.io/github/repo-size/irsyadulibad/ci4-datatables?label=size)
![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=irsyadulibad/ci4-datatables)

# ci4-datatables
Server Side Datatables Library for CodeIgniter 4 Framework

<br/>

## Deskripsi

Library untuk membuat Server Side Datatables pada CodeIgniter 4 agar menjadi **mudah** dan **singkat**


Persyaratan:
* Codeigniter 4.x
* JQuery 3.3 +
* Datatables 1.10.x 


Cara Instalasi:
* Letakkan file Datatables.php, (pada folder ```app/Libraries/```)

## Contoh Sederhana
```php
<?php namespace App\Controllers;

use CodeIgniter\Controller;
use App\Libraries\Datatables;

class Example extends Controller{
  public function datatables(){
    $datatables = new Datatables;
    $datatables->table('users')->select('name, address');
    // Memproduksi query SELECT name, address FROM users;
    echo $datatables->draw();
    // Automatically return json
  }
}
```
<br/>

## Dokumentasi

1. **Select Tabel**\
  Memilih table default
  ```php
  $datatables->table('yourTable');
  ```

2. **Get All**\
  Memilih data pada semua kolom untuk ditampilkan **$datatables->draw()** :
  ```php
  $datatables->draw();
  ```
3. **Select Field**\
  Menampilkan data pada kolom yang dipilih **$datatables->select('field1, field2, fieldN')** :
  ```php
  $datatables->select('name, address');
  ```
3. **Where Clause**\
  Menampilkan data yang telah ditentukan valuenya pada kolom teretentu **$datatables->where(['field' => 'value'])** :
  ```php
  $datatables->where(['name' => 'John']);
  ```
4. **Join Clause**\
  Menggabungkan table melalui field dan kondisi yang telah ditentuakn **$datatables->join('Table', 'Condition', 'Type[optional]')** :
  ```php
  $datatables->join('parents', 'users.id = parents.id_user');
  //Anda juga bisa menambahkan type seperti INNER JOIN, LEFT JOIN, dsb
  $datatables->join('parents', 'users.id = parents.id_user', 'INNER JOIN');
  ```
<br/>

#### Catatan
* Anda juga dapat menambahkan clausa *AND WHERE* dengan menambahkan elemen array:
```php
$datatables->where(['field1' => 'data1', 'field2' => 'data2', 'fieldN' => 'dataN']);
```
* Anda dapat menambahkan header agar data yang ditampilkan dapat dipastikan tipenya adalah JSON (optional) :
```php
header('Content-Type': 'application/json');
```
<br/>

## Author's Profile:

Github: [https://github.com/irsyadulibad]\
Website: [http://irsyadulibad.my.id]\
Facebook: [https://facebook.com/irsyadulibad.dev]
