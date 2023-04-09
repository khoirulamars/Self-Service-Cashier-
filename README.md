# Project : Self-Service Cashier
Membuat layanan kasir sederhana menggunakan bahasa pemrograman Python.

## Latar Belakang Problem
Melakukan perbaikan dalam proses bisnis pada bagian layanan perhitungan dan pembayaran di kasir supermarket. Dimana diperlukannya sebuah sistem kasir yang dapat secara cepat dan tepat mencatat dan menghitung barang pembelian dari pembeli secara otomatis dan mandiri.

## Solusi
Dibuatlah suatu sistem kasir mandiri yang sederhana dengan menggunakan bahasa pemrograman Python, yang bertujuan untuk mempermudah customer dalam bertransaksi belanja. Sistem kasir ini memiliki fitur utama yang memungkinkan customer untuk menambahkan item yang ingin dibeli beserta jumlah dan harganya. Selain itu, jika terdapat kesalahan saat melakukan input, customer dapat mengubah nama item, jumlah item, dan harga item dengan mudah. Untuk mengulang transaksi dari awal, customer juga bisa menghapus salah satu atau seluruh item sekaligus. Setelah selesai memilih item, customer dapat mengecek daftar item dalam bentuk tabel, serta menghitung total harga dan diskon yang didapatkan.

## Requirements/Objective
- Membuat proses menyelesaikan permasalahan kasir self-service untuk memudahkan proses penjualan.
- Membuat proses untuk `menambahkan barang` belanjaan.
- Membuat proses untuk `edit nama` barang belanjaan.
- Membuat proses untuk `edit jumlah` barang belanjaan. 
- Membuat proses untuk `edit harga` barang belanjaan.
- Membuat proses untuk `menghapus barang` belanjaan.
- Membuat proses untuk `menghitung total harga` barang belanjaan.
- Membuat proses untuk `menghitung diskon` barang belanjaan.
- Membuat proses untuk `mengosongkan barang` belanjaan.
- Mengecek barang belanjaan dengan `menampilkan seluruh barang belanjaan`.

## Flowchart
![Flowchart](https://user-images.githubusercontent.com/111468833/230752404-2e2f6b7b-fd9a-4d8a-bfd7-49b690b488c9.png)

## Deskripsi Module
1. Module 'main.py' memuat class Transaction yang memiliki fungsi utama dalam program kasir.
2. Module 'check_data.py' berisi validasi data yang dimasukan pelanggan, apakah data sudah benar sesuai dengan program atau belum.
3. Module 'test_case.ipynb' digunakan untuk melakukan uji coba code apakah sudah berjalan dengan baik atau belum.

## Penjelasan Fungsi pada module main.py

Terdapat class bernama Transaction yang berisi beberapa fungsi/method untuk melakukan beberapa perintah dalam program kasir.

- `__init__`. Menginisiasi variable utama pada sebuah class. Dalam hal ini adalah variable `items` yang dinisiasi.
- `add_item`. Menambahkan barang dengan format `add_item([item_name, quantity, price_per_item])` ke dalam variable `items` di dalam class.
- `delete_item`. Menghapus barang berdasarkan nama di dalam `items` jika tersedia dengan format `delete_item(item_name)`. 
- `update_item_name`. Mengganti nama barang saat ini dengan nama barang yang baru jika barang yang disebutkan tersedia dengan format `update_item_name(old_name, new_name)`.
- `update_item_qty`. Mengganti jumlah pesanan barang jika barang yang disebutkan tersedia dengan format `update_item_name(item_name, new_qty)`.
- `update_item_price`. Mengganti harga per item barang jika barang yang disebutkan tersedia dengan format `update_item_price(item_name, new_price)`.`
- `calculate_total_price`. Menghitung harga total semua barang.
- `check_order`. Menampilkan semua barang yang telah ditambahkan beserta dengan total harga keseluruhan.
- `reset_transaction`. Mengosongkan semua barang sekaligus yang telah ditambahkan.
- `total_price_print`. Menampilkan seluruh barang beserta total harga tiap barang, discount, dan total setelah diskon.
- `calculate_discount`. Menghitung jika total keseluruhan harga barang memenuhi syarat diskon. Syarat diskon adalah sebagai berikut:
	1. Jika di atas Rp 200.000 diskon sebesar 5%
	2. Jika di atas Rp 300.000 diskon sebesar 8%
	3. Jika di atas Rp 500.000 diskon sebesar 10%

## Penjelasan Fungsi pada module check_data.py

- `check_add_item`. Validasi sebelum item ditambahkan. Meliputi format penulisan dan harga barang/qty tidak boleh negatif.
- `check_update_item_name`. Validasi sebelum item diganti namanya. Meliputi format penulisan nama item baru dan nama item lama.
- `check_update_item_qty`. Validasi sebelum qty item diupdate. Meliputi format penulisan dan qty tidak boleh negatif.
- `check_update_item_price`. Validasi sebelum harga item diupdate. Meliputi format penulisan dan harga tidak boleh negatif.

## Test Case

1. Membuat ID transaksi customer:
![ID Transaksi](https://user-images.githubusercontent.com/111468833/230783580-3718a257-fcfe-4ca7-962f-e9f27aa21137.png)
Class Transaction diambil dari modul main.py
2. Customer memasukan nama item, jumlah item, dan harga barang.
![Add Item](https://user-images.githubusercontent.com/111468833/230783836-916e0ab9-ee1f-4b49-94a7-bba083c1d269.png)
![add 3 item](https://user-images.githubusercontent.com/111468833/230783983-792d3ee5-8a98-4d36-baa4-08bf7e044e0a.png)
method add_item diambil dari modul main.py digunakan untuk menambahkan item. Dalam hal ini ditambahkan tiga item seperti terlihat pada gambar diatas.
3. Melakukan update nama item, jumlah item atau harga item.
![update](https://user-images.githubusercontent.com/111468833/230784094-640d4219-e77e-4cec-baec-9bc30072c8e8.png)
4. Jika batal membeli item belanjaan, Customer bisa melakukan :

   a. Hapus salah satu item dari nama item dengan method delete_item(<nama item>)
![hapus satu](https://user-images.githubusercontent.com/111468833/230784275-8ec851f3-7f62-450d-bcc5-48978311a6d4.png)

	b. Langsung menghapus semua transaksi atau melakukan reset belanjaan.
![Hapus semua](https://user-images.githubusercontent.com/111468833/230784345-fb34a747-b7db-4bfe-8343-4247607fefe4.png)

5. Melakukan cek untuk semua belanjaan menggunakan method check_order()
![check](https://user-images.githubusercontent.com/111468833/230784529-451e4e0d-f6ea-470f-8ce7-c14e73f20cb7.png)

6. Melakukan cek total harga dengan menggunakan total_price_print()
![total](https://user-images.githubusercontent.com/111468833/230785508-5d7532cb-5d70-4eb2-ab4e-2ac18c8c3cc4.png)
