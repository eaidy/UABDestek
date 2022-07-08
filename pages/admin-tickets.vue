<template>
  <v-container class="mt-15">
    <v-form v-model="valid">
      <div class="card-bg">
        <v-row class="align-content-end">
          <v-col cols="12" md="2">
            <v-subheader class="pl-1">Gruplama</v-subheader>
            <v-select
              v-model="firstname"
              label="Gruplama Seçimi"
              solo
              dense
            ></v-select>
          </v-col>
          <v-col cols="12" md="2">
            <v-subheader class="pl-1">Başlangıç Tarihi</v-subheader>
            <v-text-field
              v-model="firstname"
              label="25.03.2022"
              solo
              dense
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="2">
            <v-subheader class="pl-1">Bitiş Tarihi</v-subheader>
            <v-text-field
              v-model="firstname"
              label="16.04.2022"
              solo
              dense
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="2">
            <v-subheader class="pl-1">Ticket Durumu</v-subheader>
            <v-select
              v-model="firstname"
              label="DOĞRU"
              solo
              dense
            ></v-select>
          </v-col>
          <v-col cols="12" md="2">
            <v-subheader class="pl-1">Kurumu</v-subheader>
            <v-text-field
              v-model="firstname"
              label="TCDD"
              solo
              dense
            ></v-text-field>
          </v-col>
          <v-col cols="12" md="2">
            <v-subheader class="pl-1"> </v-subheader> 
            <v-btn color="blue-grey" class="white--text w-100">
              Listele
            </v-btn>
          </v-col>
        </v-row>
      </div>

      <v-card
        class="mt-10 w-100 d-flex justify-content-between align-items-center"
      >
        <v-tabs>
          <v-tab>Gelen Ticketler</v-tab>
          <v-tab>Giden Ticketlar</v-tab>
        </v-tabs>
        <v-btn color="teal" class="white--text mr-2">
          Yeni Ekle
          <v-icon right dark> mdi-plus </v-icon>
        </v-btn>
      </v-card>
    </v-form>

    <v-data-table
      :headers="headers"
      :items="tickets"
      :sort-by="['queue']"
      :sort-desc="[false, true]"
      multi-sort
      class="elevation-1 mt-15"
      :footer-props="{
        'items-per-page-text': 'Sayfa başına satır'
      }"
    ></v-data-table>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      headers: [
        {
          text: "Sıra",
          align: "center",
          sortable: true,
          value: "queue",
        },
        { text: "Talep No.", value: "ticketno"},
        { text: "Tarih", value: "begindate" },
        { text: "Talep Sahibi", value: "ticketowner" },
        { text: "Kurumu", value: "institution" },
        { text: "Talep", value: "ticketsubject" },
        { text: "Sorumlu", value: "personincharge" },
        { text: "Onaylayan", value: "confirmer" },
        { text: "Durumu", value: "state" },
        { text: "Tarih", value: "enddate" },
      ],
      tickets: [
        {
          queue: 1,
          ticketno: "TIC1001",
          begindate: '23.05.2022',
          ticketowner: 'Doruk Yormaz',
          institution: 'TCDD',
          ticketsubject: 'KML dosyası yükleyememe problemi',
          personincharge: 'Bensu Keşap',
          confirmer: 'Cem Karakuş',
          state: 'DOĞRU',
          enddate: '23.05.2022'
        },
        { 
          queue: 2,
          ticketno: "TIC2038",
          begindate: '23.05.2022',
          ticketowner: 'Elif Atar',
          institution: 'TCDD',
          ticketsubject: 'Proje veri girememe problemi',
          personincharge: 'Bensu Keşap',
          confirmer: 'Cem Karakuş',
          state: 'DOĞRU',
          enddate: '23.05.2022'
        },
        {
          queue: 3,
          ticketno: "TIC1587",
          begindate: '23.05.2022',
          ticketowner: 'Önder Çelik',
          institution: 'TCDD',
          ticketsubject: 'Yeni yüklenici eklenmesi talebi',
          personincharge: 'Bensu Keşap',
          confirmer: 'Cem Karakuş',
          state: 'DOĞRU',
          enddate: '23.05.2022'
        }
      ],
    };
  },
};
</script>

<style lang="scss">
.v-text-field.v-text-field--enclosed .v-text-field__details {
  display: none;
}
</style>
