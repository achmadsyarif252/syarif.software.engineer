+++
date = '2026-06-03T21:34:41+07:00'
draft = false
title = 'Beda Curved Part 2'
tags = ["DesignUI","JetpackCompose"]
+++

Untuk membuat garis lengkung di jepatck compose dengan cara melakukan clipping pada shape bisa menggunakan perintah quadraticTo(x1,y1,x2,y2)

begini cara pakainya

```kotlin
//di sini mau buat bentuk yang mirip huruf u
class QuadraticPath:Shape{
         size: Size,
        layoutDirection: LayoutDirection,
        density: Density
    ): Outline {
        val path = Path().apply{
            moveTo(0f,0f) //posisi awal pena pojok kiri atas
            lineTo(size.width,0f) // ditarik garis ke pojok kanan atas
            val ySide = size.height - 100 // kita mau tarik agar sebelum tepat jatuh setinggi ukuran dia sudah mulai melengkung
            lineTo(size.width,ySide) // tarik garis mendekati ukuran
            quadraticTo(
                x1 = sise.width/2f, // posisi magnet mau diletakkan di tengah layar
                y1 = size.height+50 // kalau isi plus berarti nanti akan ditarik ke bawah 
                x2 = 0f // kita pengin titk horizontal terakhir itu ke aras pojok kiri bawah
                y2 = ySide // kita pengin titik vertikal terakhir itu ada di ySized jadi dia nanti setinggi lengkungan di sisi kanan seperti di  lineTo(size.width,ySide) // tarik garis mendekati ukuran
            )
            close()

        }
        return Outline.Generic(path)
    }
}

```

Contoh
```kotlin
class LatihanCurvedPath() : Shape {
    override fun createOutline(
        size: Size,
        layoutDirection: LayoutDirection,
        density: Density
    ): Outline {
        val path = Path().apply {
            moveTo(0f, 0f)
            lineTo(size.width, 0f)
            val ySize = size.height -100
            lineTo(size.width, ySize)
            quadraticTo(
                size.width / 2f,
                size.height,
                0f,
                ySize
            )
        }
        return Outline.Generic(path)
    }

}
```

Hasil 
![HasilCurved](/images/curved1.png)

sekarang dari kode tadi pengin dibuat versi seperti jembatan dia cekung ke atas maka magnet y1 pelru dinaikan ke atas jadi di kurangi nilainya

```kotlin
class LatihanCurvedPath() : Shape {
    override fun createOutline(
        size: Size,
        layoutDirection: LayoutDirection,
        density: Density
    ): Outline {
        val path = Path().apply {
            moveTo(0f, 0f)
            lineTo(size.width, 0f)
            lineTo(size.width, size.height)
            quadraticTo(
                size.width / 2f,
                size.height-200,
                0f,
                size.height
            )
        }
        return Outline.Generic(path)
    }

}
```

Output
![Curved bentuk jembatan dengan menarik magnet koordinat y ke atas (-)](/images/curved2.png)