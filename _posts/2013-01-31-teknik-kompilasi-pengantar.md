---
title: 'Teknik Kompilasi: Pengantar'
author: zaniar
layout: post
permalink: /2013/01/teknik-kompilasi-pengantar/
categories:
  - Technical
tags:
  - kompiler
  - teknik
---
Bagi programmer, kata kompiler pasti sudah sangat akrab di telinga. Tapi tidak tahu juga sih kalau sekarang. Dengan semakin populernya bahasa scripting seperti javascript atau lua, mungkin kompiler mulai kurang diminati.  
Kompiler adalah suatu program komputer yang menerima masukan program sumber (source code) dan menghasilkan suatu representasi yang dapat dieksekusi. Dieksekusi oleh apa? Dieksekusi oleh mesin. Baik mesin secara fisik maupun mesin secara virtual.  
Lalu, kenapa kita perlu kompiler? Alasannya adalah masalah bahasa. Mesin (dalam hal ini adalah komputer) memiliki bahasa yang sulit dimengerti oleh manusia. Sedangkan bahasa manusia terlalu kompleks untuk dapat dimengerti mesin. Salah satu kekompleksan bahasa manusia adalah masalah ambiguitas. Satu kata atau satu kalimat yang sama bisa memiliki arti yang berbeda tergantung konteks. Bagaimana kita menjelaskan yang mana maksud kita secara jelas kepada komputer? Sampai saat ini para ahli belum dapat melakukannya. Nah, makanya kita butuh bahasa pemrograman. Bahasa pemrograman dirancang untuk jelas, tegas, dan tidak ambigu. Pada ujungnya, kita butuh kompiler untuk menerjemahkan bahasa pemrograman ke bahasa mesin.

Kompiler dapat dibagi menjadi 2 bagian besar:

  1. Bagian Analisis
  2. Bagian Sintesis/Generator

Bagian analisis berfungsi untuk membongkar kode sumber. Sedangkan, bagian sintesis berfungsi menghasilkan representasi yang dapat dieksekusi. Kita akan lihat lebih jauh untuk masing masing bagian.

Bagian analisis terdiri dari 3 bagian:

  1. *Scanner*
  2. *Parser*
  3. *Semantic Analyzer*

*Scanner* berfungsi untuk mendekomposisi kode sumber menjadi token-token. Token adalah satuan terkecil yang memiliki makna. Contoh token adalah *variable,* operator, dan *keyword.* Selain mendekomposisi, scanner juga memeriksa apakah suatu token dikenal atau tidak. Jika suatu token tidak dikenal, makan *scanner* akan memberikan *error.*

*Parser* berfungsi untuk memeriksa tata bahasa dari kode sumber. Misalkan, ketika ditemukan token *variable,* kemudian diikuti dengan token operator assi*g*nment dan konstanta, maka baris tersebut dikenali sebagai *assignment statement.*

*Semantic Analyzer* berfungsi untuk memeriksa makna dari kode sumber. Misalkan pada kasus assignment, akan diperiksa apakah tipe *variable* dan *operand* cocok.

Bagian sintesis terdiri dari 2 bagian:

  1. Generator kode antara
  2. Optimisasi

Kedua bagian ini opsional dan saling terkait. Generator kode antara dibutuhkan karena akan mempermudah tahap optimisasi. Kode antara dibuat karena lebih mudah dioptimisasi dibandingkan, misalnya, kode dalam bahasa mesin. Optimisasi berfungsi untuk meningkatkan efisiensi program. Program yang dioptimisasi akan menghasilkan program yang lebih kecil dan/atau lebih cepat.

**disarikan dari perkuliahan Dr.Ir. Rila Mandala, M.Eng. tentang Teknik Kompilasi*