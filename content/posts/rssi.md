+++
date = '2026-06-13T23:25:32+07:00'
draft = false
title = 'Rssi'
tags = ["RFID"]
+++

RSSI (Received Strength Signal Indicator), seperti namanya ini adalah sebuah indikator seberapa kuat sinyal yang dipancarkan oleh sebuah gelombang radio,konteksnya pekerjaan saya di rfid ini berkaitan dengan seberapa jauh (mudahnya gitu) si chip dengan reader rfid, padahal pada praktiknya nilai rssi ini fluktuatif dan cenderung tidak konsisten, memang secara simpelnya semakin dekat chip rfid dengan reader atau si pembaca nilai rssi akan semakin kuat (0dbm itu kuat), semakin minus banyak semakin lemah artinya. misal -40dbm itu lebih lemah dibandingkan dengan -10dbm, intinya semakin mendekati - semakin kuat. dbm stand for desibel miliwat.

Kenapa fluktuatif dan tidak konsisten, karna itu dipengaruhi oleh berbagai faktor, secara singkat :
1.kondisi ruangan tempat chip tersebut diletakan
2.posisi orang yang melakukan scanning dan sudut pembacaan 
3.kondisi chip yang mulai melemah karna aus pemakaian juga berpengaruh
