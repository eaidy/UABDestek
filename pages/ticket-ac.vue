<template>
  <section class="search-bg search-bg--full">
    <v-container class="mt-15">
      <div class="text-center mb-15">
        <h1 class="title">UAB-UYS DESTEK TALEP SİSTEMİ</h1>
      </div>
      <v-text-field
        label="Aranacak Konu"
        placeholder="Arama Yapmak İstediğiniz Konu Giriniz"
        v-model="searchInput"
        filled
        rounded
        dense
      ></v-text-field>
      <div class="d-flex justify-space-between mt-1">
        <v-radio-group v-model="row" row class="mt-1">
          <v-radio label="Destek Talebi" value="radio-2"></v-radio>
          <v-radio label="Öneri" value="radio-3"></v-radio>
        </v-radio-group>
        <v-btn @click="dialog = true" color="blue-grey" class="ma-2 white--text" rounded>
          Destek Talebi Oluştur
          <v-icon right dark> mdi-plus </v-icon>
        </v-btn>
      </div>

      <div class="text-center">
        <v-dialog v-model="dialog" width="900">
          <v-card>
            <v-card-title class="justify-center"> Talep Oluştur </v-card-title>

            <v-divider></v-divider>

            <v-card-text class="mt-4">
              <v-container>
                <v-row>
                  <v-col cols="6" class="pl-0">
                    <v-select
                      label="Modül Seçiniz"
                      outlined
                      class="mb-6"
                      :items="modules"
                    ></v-select>
                  </v-col>
                  <v-col cols="6">
                    <v-select
                      label="Ticket Tipini Seçiniz"
                      outlined
                      class="mb-6"
                      :items="ticketTypes"
                    ></v-select>
                  </v-col>
                </v-row>
              </v-container>

              <v-text-field 
                label="Konu"
                :value="searchInput"
                outlined
                class="mb-6"
              >
              </v-text-field>

              <v-textarea 
                label="Açıklama" 
                outlined
                height="300"
              >
              </v-textarea>

              <!-- <v-row>
              <v-col cols="6">
                <v-text-field
                  label="Etiketler"
                  outlined
                  v-model="temp.tag"
                  @keyup.enter="addHandler"
                ></v-text-field>

                <div class="tags">
                  <span 
                    class="tag" 
                    v-for="tag in tags" 
                    :key="tag"
                    @click="deleteHandler(tag)"
                  >{{ tag }}</span>
                </div>

              </v-col>
              <v-col cols="6">
                <v-text-field 
                  label="İlgili Kişiler" 
                  outlined 
                  v-model="temp.person"
                  @keyup.enter="addPerson"
                >
                </v-text-field>
                <div class="tags">
                  <span 
                    class="tag" 
                    v-for="person in people" 
                    :key="person"
                    @click="deletePerson(person)"
                  >{{ person }}</span>
                </div>
              </v-col>
            </v-row> -->

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
              <div
                class="d-flex justify-space-between align-items-center w-100"
              >
                <div class="w-300" style="width: 300px">
                  <v-file-input
                    accept="image/*"
                    label="Dosya Ekleyin"
                    style="width: 300px"
                  ></v-file-input>
                </div>
              </div>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </div>
    </v-container>
  </section>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      searchInput: '',
      modules: ["Modül 1", "Modül 2", "Modül 3"],
      ticketTypes: ["Şifre Değiştirme", "Destek-Talep", "Öneri-Şikayet"],
      tags: [],
      people: [],
      temp: {
        tag: "",
        person: "",
      },
    };
  },
  methods: {
    addHandler(e) {
      if (!this.tags.includes(this.temp.tag)) {
        this.tags.push(this.temp.tag);
      }
      this.temp.tag = "";
    },
    deleteHandler(tag) {
      this.tags.splice(this.tags.indexOf(tag), 1);
    },
    addPerson() {
      if (!this.people.includes(this.temp.person)) {
        this.people.push(this.temp.person);
      }
      this.temp.person = "";
    },
    deletePerson(person) {
      this.people.splice(this.people.indexOf(person), 1);
    },
  },
};
</script>

<style>

</style>
