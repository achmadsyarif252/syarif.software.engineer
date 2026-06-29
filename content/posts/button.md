+++
date = '2026-06-29T22:50:50+07:00'
draft = true
title = 'Button'
tags = ["Compose","UI"]
+++

Perbedaan outlined button dengan button dan text button

Button dipakai untuk membuat button yang mewakili aksi utama yang memang wajib dilakukan oleh user, cirinya adalah dia warnanya penuh 

OutlinedButton dipakai untuk membuat button yang mewakili aksi pilihan artinya user tidak diwajibkan menekan tombol itu misal tombol delete, reset, cancel dsb, cirinya adalah dia warnanya hanya di bagian tepinya saja, warna utamanya transparan

Text button itu seperti teks tapi dikasih aksi on click fungsinya lebih dibawah dari button dan outlined button dari segi penekanan

contoh :

1. button 

```kotlin
  Button(
                onClick = { /* Aksi yang akan dilakukan saat tombol ditekan */ },
                modifier = Modifier.padding(16.dp).fillMaxWidth().height(44.dp),
                shape = MaterialTheme.shapes.medium,
                colors = ButtonDefaults.buttonColors(
                    containerColor = SecondaryBlue,
                    contentColor = Color.White
                )
            ) {
                Text("Hello World")
            }
```
![Button]("/images/button.png")

2. Outlined Button
```kotlin
OutlinedButton(
                onClick = { /* Aksi yang akan dilakukan saat tombol ditekan */ },
                modifier = Modifier.padding(16.dp).fillMaxWidth().height(44.dp),
                shape = MaterialTheme.shapes.medium,
                colors = ButtonDefaults.outlinedButtonColors(
                    contentColor = Color(0xFF2E7D32)
                ),
                border = BorderStroke(1.dp, Color.LightGray),
            ) {
                Text("Hello World")
            }
```
![Outlined Button]("/images/outlinedbutton.png")

3. Text button

```kotlin
TextButton(
                onClick = { /* Aksi yang akan dilakukan saat tombol ditekan */ },
                modifier = Modifier.padding(16.dp).fillMaxWidth().height(44.dp),
                shape = MaterialTheme.shapes.medium,
                ) {
                Text("Hello World")
            }
```
![Text Button]("/images/textbutton.png")