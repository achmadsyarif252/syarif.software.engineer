+++
date = '2026-06-11T21:47:15+07:00'
draft = false
title = 'Gradient'
tags = ["Compose"]
+++

Gradient adalah sebuah kombinasi antara 2 warna atau lebih yang digabungkan ke dalam suatu elemen baik box card atau surface yg mana memiliki titik awal dan titik akhir serta bentuk penyatuan yang diinginkan seperti apa, contoh kdoe

```kotlin
@Composable
fun GradientBox(){
    Box(
        modifier = Modifier.fillMaxSize()
        .background(
            brush = Brush.linearGradient(
                colors = listOf(Color.RED,Color.Blue)
            )
        )
    ){

    }
}
```
jadi buat gradient itu pakai properti brush

untuk membuat arahnya bisa pakai properti start dan end, misal
start = Offset(0f,Float.POSITIVE_INFINITY)
end = Offset(Float.POSITIVE_INFINITY,0f)
