<template>
  <v-app>
    <v-card color="grey lighten-4" flat tile>
      <v-toolbar dense>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Sıkça Sorulan Sorular</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn text class="nav-btn mr-2">
          <NuxtLink to="/admin-tickets">Admin Tickets</NuxtLink>
        </v-btn>
        <v-btn text class="nav-btn mr-2">
          <NuxtLink to="/arama-sonuc">Arama Sonuç</NuxtLink>
        </v-btn>
        <v-btn text class="nav-btn mr-2">
          <NuxtLink to="/arama">Arama</NuxtLink>
        </v-btn>
        <v-btn text class="nav-btn mr-2">
          <NuxtLink to="/my-tickets">My Tickets</NuxtLink>
        </v-btn>
        <v-btn text class="nav-btn mr-2">
          <NuxtLink to="/ticket-ac">Ticket Aç</NuxtLink>
        </v-btn>
        <v-btn text class="nav-btn mr-2">
          <NuxtLink to="/support-topics">Destek Başlıkları</NuxtLink>
        </v-btn>
      </v-toolbar>
    </v-card>

    <v-main>
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
};
</script>

<style lang="scss">
.nav-btn a {
  color: #343434;
  text-decoration: none;
}

.title {
  font-size: 2rem;
  font-weight: 70;
}

.card-bg {
  background: #f4f4f4;
  border-radius: 4px;
  padding: 10px;
}

.w-100 {
  width: 100%;
}

.align-items-center {
  align-items: center;
}

.result-date {
  color: #444;
}
</style>
