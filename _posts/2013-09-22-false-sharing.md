---
title: False Sharing
author: zaniar
layout: post
permalink: /2013/09/false-sharing/
categories:
  - Technical
tags:
  - cpu
  - false sharing
  - memori
  - smp
  - tesis
  - thread
---
Dalam sebuah sistem *multiprocessor* terdapat sebuah masalah yang disebut dengan *false sharing* <sup>[1]</sup>. Masalah *false sharing* terjadi ketika terdapat beberapa proses atau *thread* dari prosesor yang berbeda yang memodifikasi variabel-variabel yang terdapat pada *cache line* yang sama. Ilustrasi untuk kasus *false sharing* pada SMP dengan dua prosesor diberikan oleh gambar di bawah ini <sup>[2]</sup>:

[![False cache line sharing dalam SMP](https://i0.wp.com/software.intel.com/sites/default/files/m/d/4/1/d/8/5-4-figure-1.gif?resize=312%2C281)](http://software.intel.com/en-us/articles/avoiding-and-identifying-false-sharing-among-threads)

Di dalam gambar tersebut, terdapat dua *thread, thread* 0 dan *thread* 1, pada prosesor yang berbeda, CPU 0 dan CPU 1. Masing-masing *thread* memodifikasi variabel yang berbeda tetapi terdapat pada satu *cache line*. Ketika variabel pada CPU 0 berubah, *cache line* pada CPU 1 dianggap *outdated*. Begitu pula ketika variabel pada CPU 1 berubah, *cache line* pada CPU 0 dianggap *outdated*. Pada prosesor Intel, ketika ada *cache line* yang *outdated*, *cache line* tersebut akan diganti dengan *cache line* yang lebih baru yang terdapat pada memori utama. Terlihat bahwa setiap terjadi perubahan variabel menimbulkan akses ke memori utama. Akses ke memori utama memiliki latensi yang besar sehingga kondisi *false sharing* akan meningkatkan *delay.*

**Referensi:**

<sup>[1]</sup> Sae-eung, S. (2010). Analysis of False Cache Line Sharing Effects on Multicore CPUs.

<sup>[2]</sup> <http://software.intel.com/en-us/articles/avoiding-and-identifying-false-sharing-among-threads>