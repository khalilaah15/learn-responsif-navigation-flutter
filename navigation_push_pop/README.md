# Navigasi Push dan Pop di Flutter 🔄✨

Hai teman-teman Flutter Dev! 👋 Kali ini kita akan belajar tentang navigasi menggunakan **push** dan **pop** di Flutter. Navigasi ini berguna banget buat aplikasi multi-halaman yang membutuhkan perpindahan halaman yang mulus. Yuk, kita mulai eksplor! 🚀

---

## 🔮 Apa yang Akan Kamu Pelajari
- Cara menggunakan **Navigator.push** untuk berpindah ke halaman lain.
- Cara menggunakan **Navigator.pop** untuk kembali ke halaman sebelumnya.
- Contoh kode lengkap untuk implementasi push dan pop.

---

## 🖋️ Penjelasan Kode

Buka `navigation_push_pop/lib/main.dart`. Mari kita telusuri kode ini langkah demi langkah:

### 1⃣ Fungsi `main`
```dart
void main() {
  runApp(MyApp());
}
```
Kode ini adalah titik awal aplikasi Flutter. Fungsi ini menjalankan widget utama kita, yaitu `MyApp`. 🌟

### 2⃣ Widget Utama: `MyApp`
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ScreenUtilInit(
      designSize: Size(360, 690),
      builder: (context, child) {
        return MaterialApp(
          debugShowCheckedModeBanner: false,
          home: HomePage(),
        );
      },
    );
  }
}
```
- **`ScreenUtilInit`:** Membantu membuat aplikasi responsif di berbagai ukuran layar.
- **`MaterialApp`:** Membungkus aplikasi dengan material design.
- **`HomePage`:** Halaman utama aplikasi kita.

### 3⃣ Implementasi Navigasi di `HomePage`

```dart
class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Two Beautiful Buttons', style: TextStyle(fontSize: 18.sp)),
        centerTitle: true,
        backgroundColor: Colors.teal,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (context) => SecondPage()),
                );
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.pink,
                padding: EdgeInsets.symmetric(horizontal: 40.w, vertical: 20.h),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(30.r),
                ),
              ),
              child: Text(
                'Go to Second Page',
                style: TextStyle(
                  fontSize: 18.sp,
                  color: Colors.white,
                ),
              ),
            ),
            SizedBox(height: 20.h),
            ElevatedButton(
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (context) => ThirdPage()),
                );
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.blueAccent,
                padding: EdgeInsets.symmetric(horizontal: 40.w, vertical: 20.h),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(30.r),
                ),
              ),
              child: Text(
                'Go to Third Page',
                style: TextStyle(
                  fontSize: 18.sp,
                  color: Colors.white,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```
- **`Navigator.push`:** Menambahkan halaman baru ke tumpukan rute.
- **`MaterialPageRoute`:** Membuat transisi ke halaman lain.

### 4⃣ Halaman Kedua: `SecondPage`
```dart
class SecondPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Second Page', style: TextStyle(fontSize: 18.sp)),
        backgroundColor: Colors.teal,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              'Ini adalah halaman kedua! Navigasi menggunakan push.',
              textAlign: TextAlign.center,
              style: TextStyle(fontSize: 16.sp),
            ),
            SizedBox(height: 20.h),
            ElevatedButton(
              onPressed: () {
                Navigator.pop(context);
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.teal,
                padding: EdgeInsets.symmetric(horizontal: 40.w, vertical: 20.h),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(30.r),
                ),
              ),
              child: Text(
                'Back to HomePage',
                style: TextStyle(
                  fontSize: 18.sp,
                  color: Colors.white,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

### 5⃣ Halaman Ketiga: `ThirdPage`
```dart
class ThirdPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Third Page', style: TextStyle(fontSize: 18.sp)),
        backgroundColor: Colors.teal,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              'Ini adalah halaman ketiga! Navigasi menggunakan push dan pop.',
              textAlign: TextAlign.center,
              style: TextStyle(fontSize: 16.sp),
            ),
            SizedBox(height: 20.h),
            ElevatedButton(
              onPressed: () {
                Navigator.pop(context);
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.teal,
                padding: EdgeInsets.symmetric(horizontal: 40.w, vertical: 20.h),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(30.r),
                ),
              ),
              child: Text(
                'Back to HomePage',
                style: TextStyle(
                  fontSize: 18.sp,
                  color: Colors.white,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}
```

---

## 🔄 Pratinjau Output
- **HomePage:** Dua tombol untuk berpindah ke halaman kedua dan ketiga.
- **SecondPage:** Halaman kedua dengan tombol kembali.
- **ThirdPage:** Halaman ketiga dengan tombol kembali.

---

## 💡 Tips
 Selalu cek navigasi menggunakan emulator atau perangkat fisik untuk memastikan semuanya berjalan lancar.

---

Dibuat dengan ❤️ oleh [Kha](https://www.instagram.com/khalilaah.15/) | [LinkedIn](https://www.linkedin.com/in/khalilullah-nuraini-20246223b/).  Selamat belajar Flutter dan selamat bereksperimen! 🚀
