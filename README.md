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


# Hasil Output
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


Tujuan Program

Program ini mensimulasikan sistem ATM sederhana yang memungkinkan pengguna untuk melakukan tiga fungsi utama: tarik tunai, cek saldo, dan keluar dari sistem.
🔧 Bagian 1: Import Library dan Inisialisasi
```python

import sys

def atm_simulation():
    balance = 1000000

    import sys: Mengimpor modul system untuk menggunakan fungsi sys.exit()

    balance = 1000000: Set saldo awal sebesar Rp 1,000,000
```
# 📋 Bagian 2: Tampilan Awal
python
```python
print("Selamat datang di atm sederhana")
print(f"Saldo anda saat ini : Rp {balance:,.0f}")
```
Menampilkan pesan selamat datang dan saldo awal dengan format Rupiah.
#🔄 Bagian 3: Loop Menu Utama
```python

while True:
    print("\nmenu Transaksi")
    print("1. Tarik Tunai")
    print("2. Cek saldo")
    print("3. Keluar")
```
Loop infinite yang akan terus menampilkan menu sampai pengguna memilih keluar.
#💵 Bagian 4: Fitur Tarik Tunai (Opsi 1)
python
```python
if choice == '1':
    try:
        amount_to_withdraw = int(input("masukan jumlah penarikan: Rp "))
        
        # Validasi 1: Jumlah harus positif
        if amount_to_withdraw <= 0:
            print("Jumlah Penarikan harus lebih dari 0")
        
        # Validasi 2: Cek kecukupan saldo
        elif amount_to_withdraw > balance:
            print(f"Saldo tidak mencukupi. Saldo Anda: Rp {balance:,.0f}")
        
        # Jika validasi berhasil
        else:
            balance -= amount_to_withdraw
            print(f"Penarikan sebesar Rp {amount_to_withdraw:,.0f}")
            print("Penarikan Berhasil !")
            print(f"Saldo Anda sekarang : Rp {balance:,.0f}")
            
            # Cek jika saldo habis
            if balance == 0:
                print("Saldo Anda telah habis. Silahkan isi kembali")
                break
                
    except ValueError:
        print("input tidak valid. Harap masukan Angka.")
```
#Fitur Keamanan dalam Tarik Tunai:

    try-except: Menangani error jika input bukan angka

    Validasi jumlah: Harus > 0

    Cek saldo: Tidak boleh melebihi saldo tersedia

    Auto exit: Keluar otomatis jika saldo habis

#📊 Bagian 5: Fitur Cek Saldo (Opsi 2)
```python

elif choice == '2':
    print(f"Saldo Anda saat ini: Rp {balance:,.0f}")
```
Sangat sederhana - hanya menampilkan saldo terkini.
#🚪 Bagian 6: Fitur Keluar (Opsi 3)
```python

elif choice == '3':
    print("Terima kasih telah menggukan ATM kami.")
    sys.exit()

sys.exit() menghentikan program secara keseluruhan.
⚡ Bagian 7: Error Handling
python

else:
    print("Pilihan tidak valid. mohon masukan Angka 1/2/3")
```
Menangani input yang tidak valid selain 1, 2, atau 3.
#🎪 Bagian 8: Menjalankan Program
```

if __name__ == "__main__":
    atm_simulation()
```
Memastikan program hanya berjalan ketika dieksekusi langsung (bukan diimport).
