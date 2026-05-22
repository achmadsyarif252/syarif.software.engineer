+++
date = '2026-05-22T22:58:07+07:00'
draft = false
title = 'LLM Series Part 1 : Tokenisasi'
tags = ["Pengetahuan","Sains","Teknologi"]
+++

"komputer tidak mengetahui huruf atau kata dia hanya ngerti angka , makanya perlu diubah si teks yg ditanyakan oleh user menjadi struktur matematika

caranya pertama adalah dengan memecah teks yg user input ke dalam token token, nama prosesnya adalah tokenisasi proses ini dilakukan oleh program Tokenizer, nah tiap kata nanti dipecah, sebetulnya tidak spesifik dipecah tiap kata, bisa aja tiap suku kata misal "mendengarkan" bisa dipecah menjadi "Men","Dengar","Kan"

ada beberapa pertanyaan yg perlu dipahami dulu

1. kenapa dipecah menjadi suku kata kenapa tidak per kata saja atau per huruf ?

2. Siapa yang memecah kata tersebut

3. gimana penentuan kata itu nanti dipecah apa, misal mendengarkan kenapa dipecahnya menjadi men dengar kan kenapa tidak men denga rkan atau yang lainya.

4. apakah itu konsisten setiap kata tersebut akan diubah menjadi token tersebut alias sudah paten ?

Pembahasan

Tokenisasi memecah kata menjadi sekumpulan suku kata itu karna alasan komputasi dan efisiensi token, dulu ilmuan menggunakan tokeniisasi per kata (Word-based tokenization) tapi ada 3 kelemahan fatal

- banyak kata yang tidak dikenal (out of vocabulary)  bahasa manusia itu berkembang sangat cepat, muncul kata kata gaul baru, istilah serapan, slang, typo atau salah ketik, kalau pakai sistem per kata, nanti kalau user mengetik kata "menggoks" yg mana kata aneh tidak masuk ke vocabulary yg telah ditentukan nanti komputer akan bingung dan menganggapnya sebagai error , nah kalau pakai sub kata , kata menggoks mungkin akan dipecah jadi "Meng","Gok","S". karna ai sudah tahu makna awalan meng sudah ada di kamus, ai masih bisa tuh memproses teks tersebut tanpa memberikan error. lalu jika mecahnya itu per kata bahasa manusia itu kaya dengan imbuhan seperti indo,jerman dll itu satu kata dasar aja bisa jadi puluhan kata baru,misal :

dengar,mendengar,didengar,perdengarkan,pendengaran, dll

jika pakai sistem per kata di atas harus makan slot unik di kamus komputer, kalau pakai sub kata kan komputer cukup simpan token "men","di","ter" dst. dengan token dasar ini aja komputer bisa merakit puluhan variasi kata

Lalu siapa yang bertugas memecah pertanyaan user tadi ke token token dan gimana cara kerjanya ? yang menentukan adalah sebuah algoritma matematika yang mempelajari teks dalam jumlah raksasa saat model ai pertama kali dibuat. ada algoritma populer banyak dipakai llm modern seeperti keluarga gpt yaitu BPE (Byte-Pair Encoding)

gimana cara kerjanya ? algoritma ini akan membaca seluruh isi internet untuk membangun kamusnya cara kerjanya itu dari bawah ke atas ; di tahap awal per huruf pertama algoritma akan memasukkan semua huruf abjad, termasuk angka dan juga simbol ke kamusnya

lalu algoritma membaca teks raksaksa tadi dan menghitung pasangan huruf apa yang paling sering muncul berdampingan, dengan menghitung frekuensi pasangan, setelah itu proses penggabungan, misal huruf m dan e sangat sering muncul bersamaan dari data yg dimasukkan (dari semua sumber yg diberikan untuk membuat vocab)  m dan e tadi akan dimasukan sebagai token baru di kamus, proses ini akan diulang jutaan kali, jika token me sering berdampingan juga dnegan n, mereka akan digabung lagi menjadi men

proses penggabungan ini akan berhenti saat ukuran kamus sudah mencapai batas yang ditentukan, misal hanya boleh ada 100.000 token unik dalam kamus, jadi kata "mendengarkan" dipecah menjadi ["men","dengar","kan"] karena berdasarkan statistik data internet, potongan "men","dengar", dan "kan" adala kombinasi karakter yg paling sering muncul di berbagai kata dalam bahasa indonesia

nanti setiap token2 itu akan diberikan id nanti ini akan masuk kedalam kamus raksaksa".

apakah tokenisasi itu konsiten ? ya tokenizer ini bersifat deteministik jika kita memasukan kata mendengarkan dan hasilnya adalah men dengar kan maka 5 tahun lagi kalau dimasukan ke model yang sama juga bakal tetap dipecah jadi men dengar kan

jadi alurnya itu gini

user input : "Mendengarkan"

Tokenizer software (teks dipotong ke token token berdasarkan aturan statistik kamus yg paten)

Hasil potongan ["Men","dengar","kan"] nanti akan dibaca tuh di kamus token itu idnya berapa misal [1043,3253,2310]

Angka id ini nanti akan dikirim ke otak llm untuk diproses,

tapi sebelum id itu dikirim ke jaringan saraf tiruan angka itu akan diubah ke vektor koordinat yaitu dereten 4096 dimensi, tapi ini cukup kompleks bahkan versi simpelnya, kita bahas lagi di part 2

Bersambung
