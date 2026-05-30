+++
date = '2026-05-30T21:30:37+07:00'
draft = false
title = 'Dialog'
+++

Buat menampilkan dialog tinggal panggil kode dari viewmodel, akses properti di uistate yg bernilai boolean yg sudah diset untuk tampilkan dialog misal gini

Scaffold{
    if(uiState.isShowDialog){
        Dialog(
            //lanjut implementasi
        )
    }
    Column{
        ....
    }
}

buat panggil viewmodel di scren pakai ni 

@Composable
fun ContohScreen(viewmodelx:ContohViewModel = viewModel())

buat panggil uiState pakai ini
val uiState by viewModel.uiState.collectAsStateWithLifecycle()

kenapa pakai collectAsStateWithLifecycle ?

kalau colectAsState biasa dia akan terus collect perubahan data selama composable itu ada di composition tree mesikupun app sedang ada di backgroudn

kalau collectAsStateWithLifecycle dia akan berhenti koleksi kalau aplikasi masuk ke background, simpelnya fungsinya sama aja buat collect state dari viewmodel tapi collectAsStateWithLifecycle lebih hemat baterai

lalu bahas viewmodel

beda stateFLow dengan commposeState (mutableStateOf)
stateflow murni kotlin -> mutableStateOf bagian dari library copmose (android ui)

collectAsStateWithLifecycle bisa digabung dengan operator map filter dll,-> mutableStateof terbatas hanya untuk uiCopose


