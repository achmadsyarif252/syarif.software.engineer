+++
date = '2026-06-28T23:14:59+07:00'
draft = false
title = 'Slicing Basics'
tags = ["Jetpack Comose","UI"]
+++

.dp itu artinya density independent pixel konsepnya adalah dia menghitung pixel di hape dengan rumus ixel = dp * (density / 160), jadi 200 dp di hape a dengan hape b pasti sama ukuran layarnya, tapi secara persentas bisa saja berbeda, di hape keci mungkin 200dp sudah memakan 80% lebar layar, di tablet mungkin baru sekitar 20%

fill max size itu buat ambil seluruh layar yang tersedia, jika di satu elemen ada elemen lain yg di satu blok dengan maxsize, elemen tersebut akan terdorong keluar dan tidak tampil

weight untuk persentase lebar (di dalam row atau column)

item {
    untuk single elemen di compose
}

items(viewmodel.items){
untuk banyak item
}

