A. AgeEntity.java
•	Merupakan entitas dalam Room Database.
•	Berisi atribut name dan age untuk menyimpan hasil prediksi usia.
B. AgeDao.java
•	Interface Data Access Object (DAO) untuk Room.
•	Menyediakan fungsi untuk menyisipkan dan mencari data berdasarkan nama.
C. AppDatabase.java
•	Kelas konfigurasi Room database.
•	Menghubungkan database dengan AgeDao.
D. AgeApiService.java
•	Interface Retrofit untuk melakukan request ke API https://api.agify.io/?name=<nama>.
•	Menyediakan endpoint untuk memprediksi usia berdasarkan nama.
E. AgeRepositoryImpl.java
•	Implementasi dari repository. Bertanggung jawab untuk:
o	Mengambil data usia dari API melalui Retrofit.
o	Menyimpan hasilnya ke database Room.
o	Menyediakan data dalam bentuk LiveData untuk ViewModel.
F. GetAgeUseCase.java
•	Kelas opsional yang berfungsi sebagai lapisan logika bisnis.
•	Menyederhanakan pemanggilan repository dari ViewModel.
G. AgeViewModel.java
•	Komponen ViewModel yang mengelola logika aplikasi.
•	Memanggil repository untuk mengambil dan menyimpan data usia.
•	Menyediakan LiveData agar UI dapat menampilkan data secara reaktif.
H. MainActivity.java
•	Activity utama yang memuat BottomNavigationView.
•	Menyediakan wadah (fragment_container) untuk menampilkan fragment-fragment.
I. HomeFragment.java
•	Tampilan utama tempat pengguna memasukkan nama dan menekan tombol untuk memprediksi usia.
•	Hasil prediksi ditampilkan di elemen TextView dengan ID tvResult.
J. bottom_nav_menu.xml
•	File konfigurasi menu navigasi bawah (Bottom Navigation).
•	Berisi item menu seperti:
o	Home
o	Konten
o	YourMenu
o	Setting
