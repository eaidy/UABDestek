<template>
  <div>
    <section class="search-bg">
      <v-container class="mt-15">
        <div class="text-center mb-15">
          <h1 class="page-title">UAB-UYS DESTEK TALEP SİSTEMİ</h1>
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
    </section>
    <v-container>
      <div class="mt-10">
        <div class="text-left">
          <h2 class="title mb-4">Sonuçlar</h2>
        </div>
        <v-expansion-panels>
          <v-expansion-panel>
            <v-expansion-panel-header>
              Item <small class="result-date ml-4">15.12.2022</small>
              <template v-slot:actions>
                <v-icon color="primary"> $expand </v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat.
            </v-expansion-panel-content>
          </v-expansion-panel>

          <v-expansion-panel>
            <v-expansion-panel-header disable-icon-rotate>
              Item <small class="result-date ml-4">15.12.2022</small>
              <template v-slot:actions>
                <v-icon color="teal"> mdi-check </v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat.
            </v-expansion-panel-content>
          </v-expansion-panel>

          <v-expansion-panel>
            <v-expansion-panel-header disable-icon-rotate>
              Item <small class="result-date ml-4">15.12.2022</small>
              <template v-slot:actions>
                <v-icon color="error"> mdi-alert-circle </v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat.
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
        <div class="text-center mt-4">
          <v-pagination v-model="page" :length="6"></v-pagination>
        </div>
      </div>
    </v-container>
  </div>
</template>
