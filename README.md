## 📱 Flutter Responsif dan Navigasi Terbaik!
---
Untuk Materi Navigasi silakan cek 2 folder di atas ya!

Di readme ini, kita akan membahas mengenai responsif flutter🔥

Tenang ajaa, code di folder atas sudah include code responsif✨

# 📱 Flutter ScreenUtil: Rahasia Desain Responsif yang Mudah dan Cepat!

Hai, teman-teman developer! 👋
Pernah nggak, bikin aplikasi tapi tampilannya kacau di perangkat yang beda-beda? Tenang aja, kita punya solusinya: **ScreenUtil**! 🎉

ScreenUtil adalah paket yang bikin hidup kita jadi lebih gampang karena membantu membuat desain responsif tanpa ribet! Yuk, kita pelajari bareng-bareng. 🚀

---

## 🛠️ Apa itu ScreenUtil?
ScreenUtil adalah library di Flutter yang membantu kita menyesuaikan ukuran, padding, margin, dan font agar tetap proporsional di berbagai ukuran layar. Jadi, nggak ada lagi cerita tombol kepotong atau teks terlalu kecil di layar yang kecil! 😎

---

## ⚡ Instalasi
Yuk mulai dengan menginstal paketnya!

1. Tambahkan **flutter_screenutil** ke dalam file `pubspec.yaml`:

    ```yaml
    dependencies:
      flutter:
        sdk: flutter
      flutter_screenutil: ^5.6.0
    ```

2. Jangan lupa jalankan perintah berikut di terminal:

    ```bash
    flutter pub get
    ```

Done! Gampang banget, kan? 🎉 atau kamu bisa jalankan perintah di terminal VSCODE kamu kayak gini:

    ```bash
    flutter pub add flutter_screenutil
    ```

---

## 🚀 Cara Pakai

1. Import dulu ScreenUtil di file Dart kamu:

    ```dart
    import 'package:flutter_screenutil/flutter_screenutil.dart';
    ```

2. Wrap aplikasi kamu dengan **ScreenUtilInit**:

    ```dart
    import 'package:flutter/material.dart';
    import 'package:flutter_screenutil/flutter_screenutil.dart';

    void main() {
      runApp(MyApp());
    }

    class MyApp extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return ScreenUtilInit(
          designSize: Size(375, 812), // Ukuran desain awal (contoh iPhone X)
          minTextAdapt: true,
          splitScreenMode: true,
          builder: (context, child) {
            return MaterialApp(
              debugShowCheckedModeBanner: false,
              title: 'Flutter Demo',
              home: HomePage(),
            );
          },
        );
      }
    }
    ```

3. Gunakan ukuran responsif di widget kamu:

    ```dart
    import 'package:flutter/material.dart';
    import 'package:flutter_screenutil/flutter_screenutil.dart';

    class HomePage extends StatelessWidget {
      @override
      Widget build(BuildContext context) {
        return Scaffold(
          appBar: AppBar(
            title: Text(
              'ScreenUtil Demo',
              style: TextStyle(fontSize: 20.sp), // Font size responsif
            ),
          ),
          body: Center(
            child: Container(
              width: 100.w, // Lebar responsif
              height: 100.h, // Tinggi responsif
              color: Colors.blue,
              child: Center(
                child: Text(
                  'Hello!',
                  style: TextStyle(fontSize: 16.sp),
                ),
              ),
            ),
          ),
        );
      }
    }
    ```

---

## 🌟 Fitur Keren ScreenUtil
- **Ukuran responsif**: `width.w`, `height.h`, `fontSize.sp`.
- **Padding dan Margin responsif**: `EdgeInsets.symmetric(horizontal: 16.w, vertical: 8.h)`.
- **Adaptive Text**: Ukuran teks otomatis menyesuaikan layar! 🔥

---

Dibuat dengan ❤️ oleh [Kha](https://www.instagram.com/khalilaah.15/) | [LinkedIn](https://www.linkedin.com/in/khalilullah-nuraini-20246223b/).

💡 Jangan lupa kasih ⭐ di repo ini kalau kamu merasa terbantu! Semangat belajar Flutter! 😊
