## Tentang Proyek

Proyek ini dikembangkan untuk lomba **Gelar Rasa 2026** dengan memanfaatkan data kualitas udara dan data kesehatan. Analisis dilakukan untuk melihat kondisi kualitas udara berdasarkan lokasi dan waktu, serta mengeksplorasi keterkaitannya dengan data kesehatan.

Data diolah melalui tahapan preprocessing, data cleaning, penggabungan dataset, dan Exploratory Data Analysis (EDA). Hasil pengolahan digunakan sebagai sumber data untuk membangun dashboard interaktif.

## Tujuan

1. Mengidentifikasi kondisi kualitas udara berdasarkan konsentrasi polutan.
2. Menampilkan persebaran kualitas udara berdasarkan lokasi pemantauan.
3. Menganalisis pola perubahan PM2.5 berdasarkan waktu.
4. Mengeksplorasi keterkaitan kualitas udara dengan indikator kesehatan.
5. Menyajikan hasil analisis dalam bentuk dashboard yang informatif.

## Dataset

Proyek menggunakan data kualitas udara, informasi lokasi dan sensor, serta data kesehatan rumah sakit.

### Dataset final

| Nama file | Jumlah baris | Keterangan |
|---|---:|---|
| `dashboard_daily.csv` | 26.330 | Data harian kualitas udara, kesehatan, lokasi, dan sensor |
| `dashboard_pola_jam.csv` | 15.074 | Data pola PM2.5 berdasarkan jam, bulan, dan hari dalam seminggu |

**Cakupan data:**
- Periode pengamatan: 1 Januari 2024 – 14 Oktober 2026.
- Jumlah sensor: 27 sensor.
- Data harian: 26.330 baris.
- Data pola jam: 15.074 baris.

### 1. dashboard_daily.csv

Merupakan dataset utama untuk dashboard yang mencakup:

- **Informasi sensor:** ID sensor dan jumlah jam pengamatan.
- **Kualitas udara:** PM2.5, PM10, O3, NO2, SO2, dan CO.
- **Informasi cuaca:** suhu, kelembapan, dan kecepatan angin.
- **Informasi lokasi:** provinsi, kabupaten/kota, kecamatan, koordinat, dan karakteristik wilayah.
- **Informasi rumah sakit:** ID rumah sakit dan indikator kesehatan.
- **Indikator tambahan:** kategori ISPU, status keterwakilan data, rasio PM2.5 terhadap baseline, dan status data.

### 2. dashboard_pola_jam.csv

Merupakan dataset pendukung untuk analisis pola waktu, yang mencakup:

- ID sensor.
- Bulan pengamatan.
- Jam pengamatan.
- Status hari kerja atau akhir pekan.
- Rata-rata PM2.5.
- Informasi wilayah dan jenis lokasi sensor.

## Tahapan Pengolahan Data

Proses pengolahan data dilakukan melalui beberapa tahapan berikut:

1. **Data Preprocessing**  
   Membaca dataset, memeriksa struktur data, dan menyesuaikan format variabel.

2. **Data Cleaning**  
   Menangani nilai kosong, memeriksa nilai tidak valid, melakukan pemeriksaan kualitas data, serta mengidentifikasi nilai ekstrem.

3. **Data Integration**  
   Menggabungkan data kualitas udara dengan informasi sensor, lokasi, rumah sakit, dan data kesehatan.

4. **Feature Engineering**  
   Membentuk variabel waktu, menghitung jumlah jam pengamatan, menentukan hari representatif, serta membuat indikator tambahan untuk analisis.

5. **Exploratory Data Analysis (EDA)**  
   Melakukan eksplorasi distribusi polutan, pola waktu, kondisi wilayah, dan indikator kesehatan.

6. **Dashboard Development**  
   Menggunakan dataset hasil pengolahan sebagai sumber visualisasi dan analisis pada dashboard.

## Kriteria Data

Data harian dikategorikan sebagai representatif apabila memiliki minimal **18 jam pengamatan valid dalam satu hari**.

Variabel `is_representative` digunakan untuk menandai data yang memenuhi kriteria tersebut. Data yang tidak memenuhi kriteria tetap disimpan agar informasi pengamatan tidak hilang, tetapi perlu diperhatikan ketika melakukan analisis.

## Library yang Digunakan
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Kesimpulan
- Dataset final merupakan hasil pengolahan dari tahapan preprocessing dan EDA.
- Nilai ekstrem tidak dihapus untuk menentukan apakah nilai merupakan kondisi aktual atau anomali pengukuran.
- Data yang tidak memenuhi kriteria representatif tetap dipertahankan dalam dataset.
- Interpretasi hasil analisis perlu mempertimbangkan kelengkapan data, satuan pengukuran, dan karakteristik setiap sensor.
