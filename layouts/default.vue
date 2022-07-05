<template>
  <v-app dark>
    <div>
      <v-btn color="secondary">
        <NuxtLink to="/admin-tickets" style="color:antiquewhite;text-decoration:none;">Admin Tickets</NuxtLink>
      </v-btn>
      <v-btn color="secondary">
        <NuxtLink to="/arama-sonuc" style="color:antiquewhite;text-decoration:none;">Arama Sonuç</NuxtLink>
      </v-btn>
      <v-btn color="secondary">
        <NuxtLink to="/arama" style="color:antiquewhite;text-decoration:none;">Arama</NuxtLink>
      </v-btn>
      <v-btn color="secondary">
        <NuxtLink to="/my-tickets" style="color:antiquewhite;text-decoration:none;">My Tickets</NuxtLink>
      </v-btn>
      <v-btn color="secondary">
        <NuxtLink to="/ticket-ac" style="color:antiquewhite;text-decoration:none;">Ticket Aç</NuxtLink>
      </v-btn>
    </div>

    <v-main>
      <Nuxt />
    </v-main>

  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout'
}
</script>
