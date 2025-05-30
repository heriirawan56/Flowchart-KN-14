flowchart TD
    A["Mulai Program"] --> B["Inisialisasi data "]
    B --> C["Input data yang ingin diprediksi (x_input)"]
    C --> D["Ambil 3 titik data terdekat xi dan yi"]
    D --> E["Panggil fungsi lagrange_interpolation"]
    E --> F{Loop i dari 0 ke n}
    F --> G["Inisialisasi term = yi[i]"]
    G --> H{Loop j dari 0 ke n}
    H --> I{j ≠ i?}
    I -- Ya --> J["term *= (x - xi[j]) / (xi[i] - xi[j])"]
    J --> H
    I -- Tidak --> H
    H --> K["Setelah loop j, result += term"]
    K --> F
    F --> L["Return result sebagai nilai estimasi"]
    L --> M["Tampilkan hasil estimasi"]
    M --> N["Selesai"]
