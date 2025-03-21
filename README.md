| Nama                    | NIM        | Kelas   | Matkul            |
|-------------------------|------------|---------|-------------------|
| Muhammad Reval Prasetya | 312310437  | TI.23.A4| Pemrograman Web 2 |


1. Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache
klik Config -> PHP.ini

![Screenshot 2025-03-21 123847](https://github.com/user-attachments/assets/b8ba7a44-51a2-4c61-949f-abae1f2d7e90)


2. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan.
Kemudian simpan kembali filenya dan restart Apache web server.

![Screenshot 2025-03-21 124027](https://github.com/user-attachments/assets/3fe5a173-86da-4403-a2c7-a197062a1ba8)

3. Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual
dan menggunakan composer.

![Screenshot 2025-03-21 124734](https://github.com/user-attachments/assets/2273914b-d553-4bb5-b545-a140c6b133c5)

4. Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses
CLI buka terminal/command prompt.

![Screenshot 2025-03-21 124930](https://github.com/user-attachments/assets/ada133ea-44fd-491e-87de-365eecdd17cf)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat
(xampp/htdocs/lab11_ci/ci4/)

5. Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:
   **PHP SPARK**

![image](https://github.com/user-attachments/assets/b88daf73-e414-4349-b54b-354aadb92ad9)

6. Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui
pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan
kesalahan seperti berikut.

![image](https://github.com/user-attachments/assets/b5e6e606-9b78-424b-8cf1-edb1b6f72e0f)

7. Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya,
maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment
variable CI_ENVIRINMENT menjadi development.

![image](https://github.com/user-attachments/assets/4ae40147-e188-46e9-b14b-ffd0e33eed01)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
CI_ENVIRINMENT menjadi development.

![image](https://github.com/user-attachments/assets/457e7a6a-474d-4f59-8208-f1bc1cdb33be)

Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file
app/Controller/Home.php hilangkan titik koma pada akhir kode.

![image](https://github.com/user-attachments/assets/ed11d490-dc4f-431f-8d8e-ce1fd94dce35)

8. Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk
meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file **app/config/Routes.php**

![image](https://github.com/user-attachments/assets/d4492232-bce8-43f8-a232-fce17fdce80f)

9. Membuat Route Baru.
Tambahkan kode berikut di dalam **Routes.php**

$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');

![image](https://github.com/user-attachments/assets/e0df964a-7992-4fa7-964f-61993655aab0)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah
berikut.

![image](https://github.com/user-attachments/assets/97f99f5e-7f20-43a0-925a-75d44edcb3d6)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost:8080/about

![Screenshot 2025-03-21 131531](https://github.com/user-attachments/assets/2f3edd4f-6569-43a8-9800-b6273c99b5bc)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak
ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang
sesuai dengan routing yang dibuat yaitu Contoller Page.

10. Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama **page.php** pada
direktori Controller kemudian isi kodenya seperti berikut.

![image](https://github.com/user-attachments/assets/c299574b-ce23-460a-a56d-3db282e82ac3)

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah
dapat diakses.

![Screenshot 2025-03-21 132900](https://github.com/user-attachments/assets/3f5987fd-8fe8-4cf8-8a19-e067cc3fef12)

11. Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute
dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan
alamat: http://localhost:8080/page/tos

![image](https://github.com/user-attachments/assets/31cf84ba-697f-443b-87e3-dd2789cc8637)

12. Membuat View
Selanjutnya dalam membuat view untuk tampilan web agar lebih menarik. Buat file baru
dengan nama **about.php** pada direktori view **(app/view/about.php)** kemudian isi kodenya
seperti berikut.

![image](https://github.com/user-attachments/assets/daff301b-6d8d-4be0-a055-325edffa0e96)

Ubah method about pada class Controller Page menjadi seperti berikut:

<img width="627" alt="image" src="https://github.com/user-attachments/assets/9d95d4ac-d564-4f7e-a5a0-3434f6ea8e52" />

Kemudian lakukan refresh pada halaman tersebut.

![image](https://github.com/user-attachments/assets/b285993b-bf83-449c-a4d4-e283d25cb86c)

13. Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada
codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css
dan javascript terletak pada direktori public.
Buat file css pada direktori public dengan nama style.css

![image](https://github.com/user-attachments/assets/d4099607-3343-4ae5-b1e7-c972aed2c39b)

Kemudian buat folder template pada direktori view kemudian buat file **header.php**h dan
**footer.php**

![image](https://github.com/user-attachments/assets/3fb3cbc9-7f2f-4e8f-bbec-7a1abcc84c65)

File **app/view/template/footer.php**

![Screenshot 2025-03-21 134623](https://github.com/user-attachments/assets/ec607eeb-4662-459a-b9cb-64b2fe96b717)

Kemudian ubah file **app/view/about.php** seperti berikut.

![image](https://github.com/user-attachments/assets/cd5c4862-8a4b-4fab-a187-83a853bfbc5b)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![image](https://github.com/user-attachments/assets/6dbf8d4a-a53f-475c-8a27-f41291836329)
