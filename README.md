# pph-21-calculator

# 💼 PPh 21 Tax Calculation System (Indonesia)

A full-featured Python-based CLI application to manage employee income, calculate PPh 21 monthly & annually (with TER and progressive methods), and export structured payroll & tax reports.

---

This Project helps Indonesian Employers to:
1. calculate TER (Tarif Efektif Rata-rata) rates for monthly simulation,
2. Annual PPh 21 calculation using progressive tax brackets,
3. PTKP adjustment based on marital status and number of dependents.

This Program is ideal for:
1. HR & payroll professionals
2. Employees who want to understand their payslip
3. Students or learners studying tax automation
   
## 📦 Features

- Manage companies and employees
- Input monthly income & benefits
- Calculate PPh 21 tax:
  - Monthly using **TER** or **progressive**
  - Annually using **progressive tax brackets**
- View monthly salary reports & tax deductions
- Display calculation history
- Export data to `.csv` for:
  - Employee data
  - Calculation history
  - Monthly payroll reports per company

---

## 🧩 Libraries Used

| Library       | Purpose                              |
|---------------|--------------------------------------|
| `os`          | File & directory management          |
| `json`        | Store and retrieve persistent data   |
| `csv`         | Export data to `.csv` format         |
| `datetime`    | Add timestamps to exports and logs   |
| `tabulate`    | Neatly format tables in the terminal |

---

## 📂 Data Structure

Data is stored in a `data/` folder using `.json` format:

- `perusahaan.json`: List of companies
- `karyawan.json`: List of employees
- `perhitungan.json`: All PPh 21 calculation history

---

## 🚀 Main Functions

### 1. `main_menu()`
Interactive main menu to access all features.

### 2. `tambah_perusahaan()`
Add or manage company records.

### 3. `tambah_karyawan()`
Add or manage employee records with:
- PTKP status
- TER category
- Company code

### 4. `input_pemasukan()`
Record monthly salary & allowances for each employee.

### 5. `hitung_pph21_bulanan()`
Calculate monthly PPh 21 using TER or progressive method.
Saves details to history.

### 6. `hitung_pph21_tahunan()`
Calculate annual PPh 21 using accumulated data and progressive tax rules.

### 7. `tampilkan_laporan_bulan(karyawan_data, bulan, nama_pt)`
Displays monthly salary report for a company including:
- Gaji pokok, tunjangan tetap, tunjangan tidak tetap
- Iuran BPJS (JHT, JP, JKK, JKM, JKP)
- Biaya jabatan
- Penghasilan neto
- Monthly PPh 21 for each employee (if available)

### 8. `lihat_laporan_perusahaan()`
Select a company and view salary report for a chosen month.

### 9. `lihat_riwayat_perhitungan()`
View the 20 most recent PPh 21 calculations (monthly and annual):
- With timestamp, method, bruto, neto, PPh 21

### 10. `export_data()`
Export selected data to `.csv`:
- Employee list
- PPh 21 calculation history
- Full company payroll report (12 months)

---

## 🛠 Helper Functions

| Function                     | Description                                  |
|------------------------------|----------------------------------------------|
| `load_karyawan_data()`       | Load employee data from file                 |
| `load_perusahaan_data()`     | Load company data from file                  |
| `load_perhitungan_data()`    | Load tax history from file                   |
| `input_pilihan(prompt, options)` | Validated input selection               |
| `clear_screen()`             | Clears terminal screen                       |
| `pilih_perusahaan()`         | Select company (used in export/report)       |
| `get_karyawan_by_pt(kode_pt)`| Get employees by company code                |

---

## 📝 Exported CSV Columns

### Employee Data
- NIK
- Nama
- Perusahaan
- Status PTKP
- Nilai PTKP
- Kategori TER

### Tax Calculation History
- Timestamp
- Perusahaan
- NIK
- Nama Karyawan
- Periode
- Metode (TER / Progresif)
- Penghasilan Bruto
- Total Iuran BPJS
- Penghasilan Neto
- PPh 21 (Bulanan / Tahunan)

### Monthly Payroll Report
- NIK
- Nama
- Bulan
- Gaji Pokok
- Tunjangan Tetap
- Tunjangan Tidak Tetap
- Penghasilan Bruto
- Total Iuran BPJS
- Biaya Jabatan
- Penghasilan Neto

---
