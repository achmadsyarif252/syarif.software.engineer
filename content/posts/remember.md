+++
date = '2026-06-25T23:14:32+07:00'
draft = false
title = 'Remember'
tags = ["JetpackCompose","kotlin"]
+++

Remember dipakai untuk memberitahu jetpack compose bahwa variabel itu harus diingat nilainya apabila terjadi recomposition (proses menggambar ulang ui karna perubahan nilai state)

misal gini, jika kita buat variabel

```kotlin
var counter = mutableStateOf(0)

Button(
    onClick = {
        counter++
    }
){
    Tex("+")
}

yang terjadi dengan kode di atas adalah saat coutner diklik memang dia akan bertambah nialninya jadi ++ tapi karna terjadi recomposition maka variabel counter ini akan dibuat ulang lagi jadi 0 nah karna kembali ke 0 jadi tidak berubah deh di layar

```

kalau mutableState itu sebuah keyword yang digunakan untuk memebri tahu composable bahwa variabel ini perlu diawasi alias variabel ini dia nilainya akan berubah dan harus memepngaruhi ui, jika tidak pakai ini maka perubahan akan diabaikan oleh ui dan tidak terjadi recomposition

recomposition itu proses redraw ui karna terjadi perubahan state
