# Proyek: Menyelesaikan Permasalahan Perusahaan Jaya Jaya Maju

## Business Understanding

Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Perusahaan tersebut memiliki lebih dari 1000 karyawan yang tersebar di seluruh penjuru negeri.

### Permasalahan Bisnis

Karena banyaknya karyawan, perusahaan Jaya Jaya Maju masih cukup kesulitan dalam mengelola karyawan. Hal ini berimbas tingginya attrition rate (rasio jumlah karyawan yang keluar dengan total karyawan keseluruhan) hingga lebih dari 10%. Untuk mencegah naiknya attrition rate diperlukan identifikasi faktor faktor penyebabnya sehingga dapat menemukan solusi yan efektif untuk menangani masalah tersebut.

### Cakupan Proyek

Cakupan proyek meliputi dashboard yang menjawab beberapa pertanyaan berikut:
- Departemen mana yang mengalami attrition rate tertinggi ?
- Bagaimana hubungan umur dengan attrition ?
- Bagaimana hubungan gaji bulanan dengan attrition ?
- Bagaimana hubungan kerja lembur dengan attrition ?
- Bagaimana hubungan kepuasaan akan pekerjaan yang dilakukan dengan attrition ?

Selain dashboard, proyek ini juga membuat model machine learning sederhana untuk membantu manajer departemen HR dalam memprediksi attrition karyawan.

### Persiapan

Sumber data: [employee dataset](https://github.com/dicodingacademy/dicoding_dataset/tree/main/employee)

Setup environment:

```python
mkdir project_attrition_analysis
cd project_attrition_analysis
pipenv install
pipenv shell
pip install -r requirements.txt
```

## Business Dashboard

Link dashboard: [dashboard attrition analysis](https://lookerstudio.google.com/reporting/48e7ea8e-1b13-45a5-9d87-8f03d265cfb5).

Dashboard yang dibuat memiliki 5 visualisasi diantaranya: KPIs, attrition by age & gender, attrition by job satisfaction, attrition by monthly income, dan attrition by overtime. Tampilan dashboard yang dibuat adalah sebagai berikut,

![Attrition Analysis Dashboard](https://github.com/user-attachments/assets/09253733-1e50-4c13-8790-3f3cc2a3d4fd)

Gambar 1. Attrition Analysis Dashboard

Di bagian header dashboard terdapat filter departemen. Dengan menggunakan filter tersebut kita dapat mellihat data attrition tiap departemen. 
### KPIs
Visualisasi yang pertama adalah KPIs yang terdiri dari score card overall employee (jumlah keseluruhan karyawan), active employee (jumlah karyawan yang aktif), Attrition (jumlah karyawan yang meninggalkan perusahaan), attrition rate (rasio jumlah karyawan yang keluar dengan total karyawan keseluruhan), dan average monthly income (rata-rata gaji bulanan karyawan). Rincian hasil visualisasi ketika tidak diterapkan filter dan diterapkan filter untuk tiap departemen adalah sebagai berikut,
- **all department**: Overall employee = 1058, Active empployee = 879, Attrition = 179, Attrition rate = 16.92%, dan Average monthly income 6625.95
- **Research & Development**: Overall employee = 701, Active empployee = 594, Attrition = 107, Attrition rate = 15.26%, dan Average monthly income 6402.31
- **Sales**: Overall employee = 319, Active empployee = 253, Attrition = 66, Attrition rate = 20.69%, dan Average monthly income 7027.55
- **Human Resources**: Overall employee = 38, Active empployee = 32, Attrition = 6, Attrition rate = 15.79%, dan Average monthly income 7380,08

Dari rincian tersebut, dapat kita lihat bahwa departemen RnD memiliki karyawan yang lebih banyak dari departemen lain, departemen sales memiliki attrition rate tertinggi daripada departemen lain, dan rata-rata gaji bulanan tertingi adalah departemen HR.

![image](https://github.com/user-attachments/assets/f9b82fde-2e6c-4f7b-b9a4-9ff76e6135fc)

Gambar 2. Score card KPIs

### Attrition by Age & Gender
Pada bagian ini grafik yang digunakan adalah stacked bar chart yang bertujuan untuk menampilkan perbandingan jumlah attrition di setiap kelompok umur dan perbandingan antara jenis kelamin perempuan dan laki-laki. Hasil visualisasi grafik meenunjukkan bahwa kelompok umur yang paling banyak mengalami attrition adalah 26-35 tahun baik ketika tidak diterapkan filter (keseluruhan departemen) atau ketika diterapkan filter (tiap departemen). Hal ini bisa terjadi karena beberapa faktor seperti ingin mengembangkan karir mereka karena sudah merasa berpengalaman, ingin mencari pekerjaan dengan gaji atau tunjangan yang sebanding dengan pekerjaan mereka, mencari tantangan baru di perusahaan lain, dan lain-lain.

![image](https://github.com/user-attachments/assets/08c57255-5bec-425d-a68c-aab8fe877bcd)

Gambar 3. Visualisasi Attrition by age & gender

### Attrition by Job Satisfaction
Pada bagian ini grafik yang digunakan adalah bar chart yang bertujuan untuk menampilkan perbandingan jumlah attrition di setiap rating kepuasan kerja (1-4). Hasil visualisasi untuk grafik ini menunjukkan bahwa untuk keseluruhan departemen, departemen RnD, departemen sales jumlah attrition paling banyak berada pada rating 3 (puas) dan kemudian diikuti dengan rating 2 (kurang puas), sedangkan untuk departemen HR jumlah attrition paling banyak berada pada rating 2 (kurang puas) dan diikuti dengan rating 3 (puas). Penyebab hal ini bisa terjadi apabila karyawan perusahaan merasa pekerjaan yang telah dilakukan tidak sesuai dengan harapan atau bayangan awal mereka.

![image](https://github.com/user-attachments/assets/fbbb897b-bdaa-4db3-b8aa-9e3322ffc040)

Gambar 4. visualisasi attrition by job satisfaction

### Attrition by Monthly Income
Pada bagian ini grafik yang digunakan sama dengan bagian sebelumnya yakni bar chart yang bertujuan untuk menampilkan perbandingan jumlah attrition di setiap kelompok gaji. Hasil visualisasi grafik menunjukkan bahwa kelompok gaji yang paling banyak mengalami attrition adalah kelompok gaji kurang dari 5000. Hal ini bisa terjadi karena karyawan merasa tidak puas dengan gaji yang telah diberikan dan tidak sebanding dengan pekerjaan yang telah mereka lakukan.

![image](https://github.com/user-attachments/assets/f9c27cab-b0f0-459a-8d83-1dc6badd13e3)

Gambar 5. Visualisasi attrition by monthly income

### Attrition by Overtime 
Pada bagian ini grafik yang digunakan adalah doughnut chart yang bertujuan untuk menampilkan prosentase perbandingan karyawan yang mengalami overtime dan yang tidak. Hasil visualisasi grafik ini menunjukkan bahwa karyawan attrition untuk keseluruhan departemen, departemen RnD, dan departemen sales lebih banyak mengalami overtime, sedangkan di departemen HR seimbang antara yang overtime yang tidak. Overtime ini juga bisa menjadi faktor banyaknya karyawan yang meninggalkan perusahaan.

![image](https://github.com/user-attachments/assets/3b3ca3d7-edd9-432a-b79d-7c57e23bcec8)

Gambar 6. Visualisasi attrition by overtime

## Conclusion

Kesimpulan dari proyek yang sudah dikerjakan adalah sebagai berikut:
- Departemen sales adalah departemen yang mengalami attrition rate tertingi daripada departemen yang lain.
- Attrition cenderung lebih banyak terjadi ketika karyawan berada pada kelompok umur 26-35 tahun.
- Attrition lebih banyak terjadi pada karyawan yang memiliki gaji bulanan di bawah 5000.
- Attrition lebih banyak terjadi ketika karyawan overtime di pekerjaannya.
- Rating kepuasan kerja yang paling banyak mengalami attrition adalah rating 3 yang diikuti dengan rating 2.
- Model machine learning yang dibuat menggunakan model random forest memiliki akurasi sebesar 91.19%, sensitivitas sebesar 89.09%, dan spesifitas sebesar 93.05%.

### Rekomendasi Action Items

Berikan beberapa rekomendasi action items yang harus dilakukan perusahaan guna menyelesaikan permasalahan attrition rate yang tinggi.

- Manajemen beban kerja agar beban kerja yang dikerjakan karyawan lebih seimbang. 
- Pemberian bonus apabila lembur tidak bisa dihindari.
- Mengadakan penghargaan bulanan untuk mengapresiasi kinerja karyawan.
- Memberikan peluang untuk mengembangkan karir seperti pelatihan yang sesuai dengan pekerjaan mereka.
