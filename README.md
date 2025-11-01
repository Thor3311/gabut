# TUGAS 2

#  Inisialisasi Variable
```python
modal_awal = 100000000  # 100 juta rupiah
total_keuntungan = 0
```
modal_awal: Menyimpan nilai investasi awal sebesar 100 juta Rupiah
total_keuntungan: Variabel untuk menampung akumulasi keuntungan dari semua bulan

#  Data Persentase Per-Bulan
```python
persentase_laba_per_bulan = [0, 0, 0.01, 0.02, 0.06, 0.06, 0.06, 0.04]
```
Array ini menyimpan persentase laba setiap bulan dalam bentuk desimal:
    Bulan 1-2: 0% (belum menghasilkan laba)
    Bulan 3: 1% (0.01)
    Bulan 4: 2% (0.02) - seharusnya 1% menurut deskripsi
    Bulan 5-7: 6% (0.06)
    Bulan 8: 4% (0.04)

#  Proses Perhitungan Laba
```python
for bulan in range(8):
    laba_bulan_ini = modal_awal * persentase_laba_per_bulan[bulan]
    total_keuntungan += laba_bulan_ini
```
Loop ini melakukan:
    Iterasi melalui 8 bulan
    Menghitung laba setiap bulan dengan rumus: Modal Awal × Persentase Laba
    Menambahkan laba bulanan ke total keuntungan

# Output Hasil
```python
print(f"Bulan ke-{bulan + 1}: Laba = Rp{laba_bulan_ini:,.2f}")
```
Menampilkan laba per bulan dengan format Rupiah yang rapi.

# Hasil Akhir
```python
print(f"Total keuntungan selama 8 bulan adalah: Rp{total_keuntungan:,.2f}")
print(f"Modal akhir setelah 8 bulan adalah: Rp{modal_awal + total_keuntungan:,.2f}")
```
Menampilkan total keuntungan dan modal akhir (modal awal + total keuntungan).

```python
=== SIMULASI INVESTASI 8 BULAN ===

Modal awal: Rp100,000,000.00

Bulan ke-1:
  Persentase laba: 0.0%
  Laba bulan ini: Rp0.00
  Modal akhir bulan: Rp100,000,000.00

Bulan ke-2:
  Persentase laba: 0.0%
  Laba bulan ini: Rp0.00
  Modal akhir bulan: Rp100,000,000.00

Bulan ke-3:
  Persentase laba: 1.0%
  Laba bulan ini: Rp1,000,000.00
  Modal akhir bulan: Rp101,000,000.00

Bulan ke-4:
  Persentase laba: 1.0%
  Laba bulan ini: Rp1,010,000.00
  Modal akhir bulan: Rp102,010,000.00

Bulan ke-5:
  Persentase laba: 6.0%
  Laba bulan ini: Rp6,120,600.00
  Modal akhir bulan: Rp108,130,600.00

Bulan ke-6:
  Persentase laba: 6.0%
  Laba bulan ini: Rp6,487,836.00
  Modal akhir bulan: Rp114,618,436.00

Bulan ke-7:
  Persentase laba: 6.0%
  Laba bulan ini: Rp6,877,106.16
  Modal akhir bulan: Rp121,495,542.16

Bulan ke-8:
Bulan ke-7:
  Persentase laba: 6.0%
  Laba bulan ini: Rp6,877,106.16
  Modal akhir bulan: Rp121,495,542.16

Bulan ke-8:
  Persentase laba: 4.0%
  Laba bulan ini: Rp4,859,821.69
  Modal akhir bulan: Rp126,355,363.85

==================================================
HASIL AKHIR:
Total keuntungan selama 8 bulan: Rp26,355,363.85
Modal akhir setelah 8 bulan: Rp126,355,363.85
Return on Investment (ROI): 26.36%
```
