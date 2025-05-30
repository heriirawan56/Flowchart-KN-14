# Flowchart-KN-14
Naon we sa jadina lah nya
graph TD
    A[Mulai] --> B(Inisialisasi Aplikasi: Muat library, atur default waktu & lokasi, siapkan UI);

    B --> C{Loop Utama Program};

    C --> D(Tampilkan Tampilan Saat Ini: Visual Bulan, Info Gerhana, UI Kontrol);
    D --> E{Tunggu Interaksi Pengguna};

    E -- Klik Tombol 'Keluar' --> Z[Selesai];
    E -- Ubah Tanggal/Waktu --> F(Update Waktu Simulasi);
    E -- Ubah Lokasi Pengamat --> G(Update Lokasi Pengamat);
    E -- Kontrol Animasi (Play, Pause, Speed) --> H(Sesuaikan Status & Kecepatan Animasi);
    E -- Perubahan Pengaturan Tampilan (Zoom, Perspektif) --> I(Update Parameter Visualisasi);
    E -- Tidak Ada Interaksi (Jika Animasi Aktif) --> F_ANIM(Update Waktu Simulasi Otomatis Sesuai Kecepatan Animasi);

    F --> J(Mulai Blok Perhitungan Inti);
    G --> J;
    H -- Jika Mempengaruhi Waktu --> J;
    I -- Jika Mempengaruhi Data Dasar --> J;
    F_ANIM --> J;

    subgraph Blok Perhitungan Inti
        direction LR
        J_START(Mulai Perhitungan) --> K(Ambil Waktu Simulasi & Lokasi Pengamat Saat Ini);
        K --> L(Hitung Posisi Akurat: Matahari, Bumi, Bulan);
        L --> M(Hitung Fase Bulan: % Iluminasi, Nama Fase, Sudut Fase);
        M --> N{Periksa Gerhana Matahari};
        N -- Ya --> O(Hitung Detail Gerhana Matahari: Tipe, Waktu Kontak, Durasi, Magnitudo, Visual);
        N -- Tidak --> P;
        O --> P{Periksa Gerhana Bulan};
        P -- Ya --> Q(Hitung Detail Gerhana Bulan: Tipe, Waktu Kontak, Durasi, Magnitudo, Visual);
        P -- Tidak --> R;
        Q --> R(Siapkan Semua Data untuk Visualisasi: Gambar Fase Bulan, Teks Info, Data Gerhana jika ada);
        R --> J_END(Selesai Perhitungan);
    end

    J_END --> D;
