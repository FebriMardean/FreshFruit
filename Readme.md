# Fresh Fruit

Aplikasi ini berisi tentang keranjang buah dengan cara penerapan pola MVC

# Scope & Functionalities

- User dapat menginput buah
- Jika keranjang penuh maka akan muncul tulisan warning


# How does it works?

Diawali dari method `MainWindow` pada class MainWindow.xaml.cs
```csharp
    public MainWindow()
        {
            InitializeComponent();

            Bucket keranjangBuah = new Bucket(2);
            BucketController bucketController = new BucketController(keranjangBuah, this);

            toni = new Seller("toni", bucketController);

            ListBoxBucket.ItemsSource = keranjangBuah.findAll();
        }
```

Jika keranjang berhasil diisi dan sudah penuh source codenya ada pada `BucketController.cs`

```csharp
    public void addFruit(Fruit fruit)
            {
                if (bucketIsOverload())
                {
                    eventListener.onFailed("Ops, keranjang penuh");
                }
                else
                {
                    this.bucket.insert(fruit);
                    eventListener.onSucceed("Yey, berhasil ditambahkan");
                }
            }
``` 


# Tugas

1. Apa fungsi BucketEventListener?
- Untuk menerima berita dan memanggil fraamework sehingga muncul pada tampilan jika user mengklid add. Kemudian , ```void onSucceed(string message)``` sebagai method untuk menambahkan item pada keranjang buah, dan ```void onFailed(string message)``` untuk menghapus item pada keranjang buah.

2. Pembahasan Alur
- Membuat program keranjng buah yang bisa menmbahkan atau mengurangi buah yang di inginkan dan ada maksimal item yang dapat dimasukkan kedalam keranjang
- Pertama membuat assets, yaitu berisikan daftar buah yang diinginkan, ada anggur, pisang, jeruk daan apel
- Lalu membuat model, yaitu berisikan bucket atau keranjang untuk menambah buah, bucketeventlistener sebagai method agar buah berhasil ditambahkan atau dikurangi, lalu fruit untuk pemanggilan buah, lalu seller sebagai tempat penjualan buahnya.
- Setelah itu membuaat controller, yaitu bucket controller untuk mengatur keranjang buah yang sudah berisi buah. Jika keranjang penuh maka akan keluar tulisan ups keranjang penuh
- Lalu main window, berisikan coding dari semua item diatas dan juga berapa output layar dalam berbelanja buah. Menampilkan informasi buah apa saja yang dibeli, berapa jumlah maksimal buah, dan dapat mengurai buah dari keranjang.
     