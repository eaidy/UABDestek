<template>
  <v-container class="mt-15">
    <v-card class="w-100 d-flex justify-content-between align-items-center">
      <v-tabs>
        <v-tab>Destek Taleplerim</v-tab>
      </v-tabs>
      <v-btn color="green" class="white--text mr-2">
        Yenile
        <v-icon right dark> mdi-plus </v-icon>
      </v-btn>
      <v-btn color="teal" class="white--text mr-2">
        Yeni Destek Talebi
        <v-icon right dark> mdi-plus </v-icon>
      </v-btn>
    </v-card>

    <v-data-table
      :headers="headers"
      :items="tickets"
      :sort-by="['calories', 'fat']"
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
        { text: "Tarih", value: "begindate" },
        { text: "Talep Sahibi", value: "ticketowner" },
        { text: "Kurumu", value: "institution" },
        { text: "Talep", value: "ticketsubject" },
        { text: "Sorumlu", value: "personincharge" },
        { text: "Onaylayan", value: "confirmer" },
        { text: "Durumu", value: "state" },
        { text: "Tarih", value: "enddate" }
      ],
      tickets: [
        {
          queue: 1,
          begindate: '23.05.2022',
          ticketowner: 'Doruk Yormaz',
          institution: 'TCDD',
          ticketsubject: 'KML dosyası yükleyememe problemi',
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
