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

    <div class="text-center">
      <v-dialog v-model="dialog" width="800">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="red lighten-2" dark v-bind="attrs" v-on="on">
            Click Me
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="text-h5 grey lighten-2">
            Mesaj Gönder
          </v-card-title>

          <v-card-text class="mt-4">
            <v-text-field label="Outlined" outlined class="mb-6"></v-text-field>
            <v-text-field label="Outlined" outlined class="mb-6"></v-text-field>
            <v-text-field label="Outlined" outlined></v-text-field>
            <div class="d-flex mt-8">
              <v-btn color="primary" @click="dialog = false"> Gönder </v-btn>
              <v-btn
                color="secondary"
                text
                @click="dialog = false"
                class="ml-4"
              >
                İptal
              </v-btn>
            </div>
          </v-card-text>

          <v-divider></v-divider>

          <v-card-actions>
            <v-spacer></v-spacer>
            <div class="d-flex justify-space-between align-items-center w-100">
              <div class="w-300" style="width: 300px">
                <v-file-input
                  accept="image/*"
                  label="Dosya Ekleyin"
                  style="width: 300px"
                ></v-file-input>
              </div>
              <v-btn color="primary" text @click="dialog = false">
                Çıkış
              </v-btn>
            </div>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
    };
  },
};
</script>
