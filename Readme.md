# Currency Apps
Rancangan aplikasi yang akan dibuat kali ini adalah konversi mata uang dari dollar ke rupiah.
1 dollar akan kita anggap senilai Rp. 15000

# Function
1. Pengguna dapat memasukkan nominal berupa angka.
2. Pengguna akan mendapat pesan salah "Invalid" jika memasukkan huruf atau karakter.
3. Untuk melihat hasil konversi klik tombol hitung.

# How Does it works?
Diawali dari method `MainWindows` pada class `MainWindows.xaml.cs` kita mendeklarasikan fungsi dari `CurrencyController.cs` untuk menyimpan method yang akan digunakan dalam program tersebut.

```csharp
public MainWindow()
        {
            InitializeComponent();
            currencyController = new CurrencyController();
        }
```

Logika prhitungan ada pada class `CurrencyController.cs` sebagai berikut

```csharp
public string usdToIdr(string nominal)
        {
            var nominalDouble = Convert.ToDouble(nominal);
            var result = nominalDouble * 15000;
            return Convert.ToString(result);
        }
        public Boolean isAllowed(string nominal)
        {
            Regex regex = new Regex("[^0-9.-]+");
            return !regex.IsMatch(nominal);
        }
```
Kegunaan method isAllowed adalah untuk menentukan text yang dimasukkan sesuai atau tidak.
Sedangkan fungsi regex untuk pencarian angka yang telah dimasukkan dalam textbox.