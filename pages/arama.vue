<template>
  <v-container class="mt-15">
    <div class="text-center mb-15">
      <h1 class="title">UAB-UYS DESTEK TALEP SİSTEMİ</h1>
    </div>
    <v-text-field
      label="Aranacak Konu"
      placeholder="Arama Yapmak İstediğiniz Konu Giriniz"
      filled
      rounded
      dense
    ></v-text-field>
    <div class="d-flex justify-space-between mt-1">
      <v-radio-group v-model="row" row class="mt-1">
        <v-radio label="Şifre" value="radio-1"></v-radio>
        <v-radio label="Destek Talebi" value="radio-2"></v-radio>
        <v-radio label="Öneri / Şikayet" value="radio-3"></v-radio>
      </v-radio-group>
      <v-btn color="blue-grey" class="ma-2 white--text" rounded>
        Talep Oluştur
        <v-icon right dark> mdi-plus </v-icon>
      </v-btn>
    </div>
  </v-container>
</template>
