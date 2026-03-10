Bike Sharing KPI Analysis
Project Overview

Project ini bertujuan untuk menganalisis pola penggunaan layanan bike sharing menggunakan data perjalanan (trip data) yang tersedia dalam beberapa file CSV. Analisis dilakukan menggunakan Python dengan pendekatan data analytics berbasis KPI (Key Performance Indicator) untuk memahami pola penggunaan layanan serta menentukan prioritas peningkatan layanan.

Dataset yang digunakan berisi informasi perjalanan sepeda seperti waktu mulai perjalanan, waktu selesai perjalanan, tipe pengguna, tipe sepeda, serta stasiun awal perjalanan.

Objectives

Tujuan utama dari project ini adalah:

Menggabungkan beberapa file dataset perjalanan sepeda menjadi satu dataset analisis.

Melakukan preprocessing data untuk membersihkan data yang tidak valid.

Menghitung beberapa KPI utama dan KPI turunan untuk memahami pola penggunaan layanan.

Membuat visualisasi data untuk melihat tren penggunaan bike sharing.

Memberikan rekomendasi keputusan berbasis data terkait peningkatan stabilitas layanan.

Key Performance Indicators (KPI)
KPI Utama

Peak Reliability / Stable Service Index

KPI ini digunakan untuk mengukur kestabilan layanan bike sharing dalam melayani permintaan pengguna, terutama pada jam sibuk dan lokasi dengan intensitas penggunaan tinggi.

KPI Turunan
Member Share

Member Share merupakan persentase perjalanan yang dilakukan oleh pengguna berstatus member dibandingkan dengan total perjalanan.

Formula:

Member Share = jumlah trip oleh member / total trip × 100%

KPI ini digunakan untuk mengukur tingkat loyalitas pengguna terhadap layanan.

Peak Intensity

Peak Intensity merupakan persentase perjalanan yang terjadi pada jam sibuk.

Jam sibuk yang digunakan dalam analisis ini adalah:

07:00 – 09:00
16:00 – 18:00

Formula:

Peak Intensity = jumlah trip pada jam sibuk / total trip × 100%

KPI ini digunakan untuk melihat tekanan penggunaan layanan pada periode tertentu.

Top Station Concentration

Top Station Concentration menunjukkan persentase perjalanan yang terkonsentrasi pada 10 stasiun dengan jumlah perjalanan tertinggi.

Formula:

Top 10 Station Trips / Total Trips × 100%

KPI ini membantu mengidentifikasi hotspot penggunaan layanan.

Guardrail KPI
Median Trip Duration

Guardrail digunakan untuk memastikan bahwa peningkatan penggunaan layanan tidak menurunkan kualitas perjalanan.

Formula:

Median Trip Duration = median(ended_at − started_at)
Data Processing Steps

Analisis dilakukan melalui beberapa tahapan utama:

Load Dataset

Semua file CSV yang berada dalam folder dataset akan digabungkan menjadi satu dataframe menggunakan library pandas.

Data Cleaning

Tahapan preprocessing meliputi:

konversi kolom waktu menjadi format datetime

menghapus data dengan waktu perjalanan tidak valid

menghitung durasi perjalanan

menghapus perjalanan dengan durasi negatif

Feature Engineering

Beberapa variabel tambahan dibuat untuk analisis, seperti:

month

hour

weekday

day_type (weekday / weekend)

peak hour indicator

KPI Calculation

Beberapa metrik utama yang dihitung antara lain:

Total Trips

Member Share

Peak Intensity

Median Trip Duration

Top Station Concentration

Data Visualization

Beberapa visualisasi yang dihasilkan dari analisis ini antara lain:

Monthly Total Trips

Grafik ini menunjukkan tren jumlah perjalanan setiap bulan.

Trips by Hour

Visualisasi ini menunjukkan distribusi perjalanan berdasarkan jam dalam satu hari serta membandingkan pola perjalanan antara weekday dan weekend.

Top 10 Start Station

Grafik ini menampilkan sepuluh stasiun dengan jumlah perjalanan tertinggi.

Decision Insight

Berdasarkan hasil analisis data, program yang dipilih adalah:

Option B – Peak Reliability

Alasan pemilihan program ini adalah karena analisis menunjukkan adanya lonjakan penggunaan layanan pada jam sibuk serta adanya konsentrasi perjalanan pada beberapa stasiun utama. Oleh karena itu, peningkatan stabilitas layanan pada jam sibuk menjadi prioritas utama.

Technologies Used

Project ini menggunakan beberapa library Python berikut:

pandas

matplotlib

glob

os

How to Run the Project

Pastikan Python sudah terinstall.

Install library yang diperlukan:

pip install pandas matplotlib

Letakkan semua file dataset CSV dalam satu folder.

Jalankan script Python:

python analysis.py

Script akan menampilkan:

hasil KPI

tabel analisis

visualisasi grafik
