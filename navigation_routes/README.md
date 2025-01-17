# Navigasi dengan Named Routes dan Arguments di Flutter 🚀🛤️

Halo teman-teman Flutter Dev! 👋 Kali ini kita akan belajar bagaimana menggunakan **Named Routes** untuk navigasi di Flutter, sekaligus mengirim **arguments** ke halaman lain. Yuk, simak sampai selesai! 🌟

---

## 🔮 Apa yang Akan Kamu Pelajari
- Bagaimana cara menggunakan **Named Routes**.
- Mengirim data (arguments) melalui Named Routes.
- Menangani arguments di halaman tujuan.

---

## 🖋️ Penjelasan Kode

### 1⃣ `main.dart`
Kode utama untuk mendefinisikan routes dan memulai aplikasi.

```dart
import 'package:flutter/material.dart';
import 'package:flutter_screenutil/flutter_screenutil.dart';
import 'package:navigation_routes/homePage.dart';
import 'package:navigation_routes/secondPage.dart';
import 'package:navigation_routes/thirdPage.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ScreenUtilInit(
      designSize: Size(360, 690),
      builder: (context, child) {
        return MaterialApp(
          debugShowCheckedModeBanner: false,
          initialRoute: '/',
          routes: {
            '/': (context) => HomePage(),
            '/second': (context) => SecondPage(),
            '/third': (context) => ThirdPage(),
          },
        );
      },
    );
  }
}
```

### 2⃣ `homePage.dart`
Halaman utama dengan dua tombol navigasi.

```dart
import 'package:flutter/material.dart';
import 'package:flutter_screenutil/flutter_screenutil.dart';

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Navigation Routes', style: TextStyle(fontSize: 18.sp)),
        centerTitle: true,
        backgroundColor: Colors.teal,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              onPressed: () {
                Navigator.pushNamed(context, '/second');
              },
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.pink,
                padding: EdgeInsets.symmetric(horizontal: 40.w, vertical: 20.h),
                shape: RoundedRectangleBorder(
                  borderRadius: BorderRadius.circular(30.r),
                ),
              ),
              child: Text(
                'Button 1',
                style: TextStyle(
                  fontSize: 18.sp,
                  color: Colors.white,
                ),
              ),
            ),
            SizedBox(height: 20.h),
            ElevatedButton(
              onPressed: () {
                Navigator.pushNamed(
                  context,
                  '/third',
                  arguments: {'data': 'Hello from HomePage'},
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
                'Button 2',
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

### 3⃣ `secondPage.dart`
Halaman kedua tanpa arguments.

```dart
import 'package:flutter/material.dart';
import 'package:flutter_screenutil/flutter_screenutil.dart';

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
              'Ini adalah contoh penggunaan navigasi pushNamed yang menggunakan routes',
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
                'Back to MyApp',
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

### 4⃣ `thirdPage.dart`
Halaman ketiga yang menerima arguments.

```dart
import 'package:flutter/material.dart';
import 'package:flutter_screenutil/flutter_screenutil.dart';

class ThirdPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Menerima arguments
    final args = ModalRoute.of(context)?.settings.arguments as Map;
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
              args != null ? args['data'] : 'No Data Received',
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
                'Back to MyApp',
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

## 🚀 Cara Kerja
1. **Named Routes:** Didefinisikan di `MaterialApp` melalui properti `routes`.
2. **Navigasi ke Halaman Lain:** Gunakan `Navigator.pushNamed` untuk berpindah halaman.
3. **Mengirim Arguments:** Kirim data melalui parameter `arguments`.
4. **Menerima Arguments:** Tangkap data menggunakan `ModalRoute.of(context)?.settings.arguments`.

---

## 🔄 Pratinjau Output
1. **Button 1:** Membuka halaman kedua tanpa arguments.
2. **Button 2:** Membuka halaman ketiga dengan arguments.

---

Dibuat dengan ❤️ oleh [Kha](https://www.instagram.com/khalilaah.15/) | [LinkedIn](https://www.linkedin.com/in/khalilullah-nuraini-20246223b/). Happy coding! 💻✨
