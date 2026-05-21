+++
date = '2026-05-21T22:17:06+07:00'
draft = false
title = 'Backpropagation'
tags = ["Tech","Pengetahuan","AI"]
+++

Backpropagation adalah proses komputer memberitahukan layer parameter secara mundur dari layer paling terakhir hingga sampai ke layer pertama kali saat suatu kata itu masuk , apa yang dibertahu ? yg diberi tahukan adalah informasi bahwa koordinat yg dibawa oleh setiap layer itu apakah benar atau salah atas hasil tebakan yang dilakukan layer paling atas , jadi misal ada kata "Kucing itu sedang ...." nah pas training kata terbang ternyata kata terbang itu salah tidak nyambung dnegan kalimat tersebut maka dilakukan backpropagation untuk memberikan nilai faktor pengali (knop parameter) ke kata terbang itu jauh posisinya supaya di masa depan, kalau ada kata kucing layer layer tersebut tidak mengantarkan sinyal menuju koordinat terbang.


Untuk mengatur nilai tiap sirkuitnya itu perlu dilakukan perhitungan matematis menggunakan konsep turunan 

Series yang sangat kompleks bersambung ke part selanjutnya esok hari akan bahas mengenai matriks embedding, pre training, kenapa llm itu perlu waktu lama dan membutuhkan komputer yang sangat banyak

Singkatnya adalah kenapa lama karna perlu melakukan training, apa yang dilakukan di training ? jadi ratusan ribu kata (vocabulary) itu akan dilakukan perkalian matematika matriks sebanyak triliunan kali proses ini bikin lama lalu untuk melakukan operasi perkalian yang begitu masif pasti butuh komputer yang sangat canggih dan banyak.