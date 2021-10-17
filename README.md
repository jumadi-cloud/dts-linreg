# Deployment Model Regresi Linier

## Deskripsi singkat

Repository ini berisi semua file yang dibutuhkan untuk melakukan deployment model Machine Learning Regresi Linier. Adapun model yang digunakan merupakan model untuk memprediksi biaya asuransi berdasarkan:

-   `Age` atau usia dengan tipe data integer (bilangan bulat)
-   `Sex` atau jenis kelamin yakni `Male` atau `Female`
-   `Smoker` atau status perokok yakni `Yes` atau `No`

#

## Sekilas mengenai input model

Agar dapat memprediksi biaya asuransi, data input model harus mengikuti format sebagai berikut:\
`[Age, Sex(Female), Sex(Male), Smoker(No), Smoker(Yes)]`

Sebagai contoh:\
Age: 20\
Sex: Male\
Smoker: No

Akan diubah menjadi:\
`[20, 0, 1, 1, 0]`

#

## Folder, file, dan kegunaannya

-   templates/
    -   index.html --> Berisi template website
-   app.py --> Berisi konfigurasi route untuk API
-   model.pkl --> Model Regresi Linier yang sudah di-training
-   request.py --> Berisi percobaan pemanggilan API dengan payload data JSON
-   requirements.txt --> Berisi daftar dependency/package Python yang diperlukan untuk menjalankan API dan model Regresi Linier

#

## Cara menjalankan API pada komputer Anda

### Menjalankan API

1. Pastikan Anda sudah menginstall Anaconda
1. Buka terminal/command prompt/power shell
1. Buat virtual environment dengan\
   `conda create -n <nama-environment> python=3.9`
1. Aktifkan virtual environment dengan\
   `conda activate <nama-environment>`
1. Install semua dependency/package Python dengan\
   `pip install -r requirements.txt`
1. Jalankan API menggunakan perintah\
   `python app.py`

### Akses melalui Website

Setelah API berjalan:

1. Anda akan diberikan URL untuk membuka website berupa `localhost:5000/` atau `127.0.0.1:5000/`
1. Buka URL dengan browser, coba masukkan data yang ingin di prediksi
1. Anda akan diberikan estimasi biaya asuransi pada sisi kanan halaman website

### Mencoba Akses API menggunakan payload JSON

Setelah API berjalan:

1. Buka terminal/comand prompt/power shell
1. Jalankan perintah `python request.py`
1. Setelah berhasil dieksekusi, Anda akan diberikan data response berupa JSON juga seperti contoh berikut:\
   `{'Age': 20, 'Insurance Cost': 3146.79, 'Sex': 'Male', 'Smoker': 'No'}`
1. Hasil prediksi biaya asuransi terdapat pada value dari key `'Insurance Cost'` yang dapat Anda manfaatkan untuk aplikasi lain.
