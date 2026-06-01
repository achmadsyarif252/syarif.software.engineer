+++
date = '2026-06-01T19:47:30+07:00'
draft = false
title = 'Clip'
+++

Clip Shape manual di kotlin

bayangkan sedang melukis di kanvas, 2d, koordinat x dan y, x garis horizontal, y vertikal

x 0, dia akan di pojok kiri layar, y 0 maka dia akan di atas, kalau x0,y0 maka dia akan di pojok kiri atas, x = 100 (semakin besar semakin ke kanan, nilai max = x = size.width), maka dia akan ke kanan, kalau x = size.width dan y = 0 maka dia akan ada di pojok kanan atas

kalau x = size.width, dan y = size.height, maka titik akan ada di pojok kanan bawah

ada 4 printah utama 
moveTo (meletakkan kuas di titik yg diinginkan), misal moveTo(0f,0f) dia akan ada di pojok kiri atas

lineTo(size.width,0) artinya adalah tancapkan pena dari koordinat terakhir lalu goreskan ke koordinat yg ada di lineTo, ini berguna untuk membuat garis 

quadratic (x1,y1,x2,y2) untuk membuat garis lengkung
tarik kurva melengkung dari posisi terakhir pena menuju x2 dan y2 tapi jalurnya harus ditarik oleh magnet yang ada di x1,y1, pena tidak pernah sentuh x1,y1, magnet hanya untuk menarik lengkungan saja

close : (kunci/segel bidnag) tarik pena dari posisi terakhir ke posisi awal saat pertama memanggil moveTo()

latihan menggambar
