<template>
  <div>
    <section class="search-bg">
      <v-container>
        <v-row class="ma-4">
<<<<<<< HEAD
            <v-col cols="12">
                <div class="header">
                    Uygun Başlıklar Ata
                </div>
                <div>
                    <v-breadcrumbs
                        :items="links"
                        divider="/"
                        class="justify-center"
                    ></v-breadcrumbs>
                </div>
                <v-divider></v-divider>
                <br />
                <v-text-field
                    label="Arama"
                    placeholder="Arama Yapmak İstediğiniz Konu Giriniz"
                    outlined
                ></v-text-field>
            </v-col>
        </v-row>

        <v-row class="items-section elevation-2">
            <v-col col="6">
                <div>
                    <div class="sub-header ml-3 mb-3">
                        <v-icon class="mb-1">mdi-file-document-check</v-icon> Destek Talepleri
                    </div>
                    <v-divider></v-divider>
                    <div class="ml-6 mt-4">
                        <div v-for="ticket in tickets" :key="ticket.id" class="mb-1">
                            <v-icon small>mdi-pencil</v-icon>
                            <span class="ml-2 list-element">
                                <a href="/support-topics">
                                    {{ ticket.subject }}
                                </a>
                            </span>
                        </div>
                    </div>
                </div>
            </v-col>
            <v-col col="6">
                <div>
                    <div class="sub-header ml-3 mb-3">
                        <v-icon class="mb-1">mdi-file-document-edit</v-icon> Öneri ve Şikayetler
                    </div>
                    <v-divider></v-divider>
                    <div class="ml-6 mt-4">
                        <div v-for="suggest in suggests" :key="suggest.id" class="mb-1">
                            <v-icon small>mdi-pencil</v-icon><span class="ml-2 list-element"><a href="/support-topics">{{ suggest.subject }}</a></span>
                        </div>
                    </div>
                </div>
            </v-col>
=======
          <v-col cols="12">
            <div class="text-center">
              <div class="page-title">Uygun Başlıklar</div>
              <div>
                <v-breadcrumbs
                  :items="links"
                  divider="/"
                  class="justify-center"
                ></v-breadcrumbs>
              </div>
            </div>
            <v-text-field
              class="mt-15"
              label="Arama"
              placeholder="Arama Yapmak İstediğiniz Konu Giriniz"
              background-color="#fff"
              filled
              rounded
              dense
            ></v-text-field>
          </v-col>
>>>>>>> cd1b171768eed2bbf5fef2c5ca5637e6dad5e1b6
        </v-row>
      </v-container>
    </section>
    <v-container class="mt-8">
      <v-row class="">
        <v-col col="6">
          <div class="default-card-plain">
            <div class="sub-header mb-3">
              <v-icon class="mb-1">mdi-file-document-check</v-icon> Destek
              Talepleri
            </div>
            <v-divider></v-divider>
            <div class="mt-4">
              <div
                v-for="ticket in tickets"
                :key="ticket.id"
                class="topic-list-item"
              >
                <v-icon small>mdi-file-document</v-icon>
                <span class="ml-2 list-element">
                  <a href="/support-topics">
                    {{ ticket.subject }}
                  </a>
                </span>
              </div>
            </div>
          </div>
        </v-col>
        <v-col col="6">
          <div class="default-card-plain">
            <div class="sub-header mb-3">
              <v-icon class="mb-1">mdi-file-document-edit</v-icon> Öneri ve
              Şikayetler
            </div>
            <v-divider></v-divider>
            <div class="mt-4">
              <div
                v-for="suggest in suggests"
                :key="suggest.id"
                class="topic-list-item"
              >
                <v-icon small>mdi-file-document</v-icon
                ><span class="ml-2 list-element"
                  ><a href="/support-topics">{{ suggest.subject }}</a></span
                >
              </div>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          text: "Destek-Talep",
          disabled: false,
          href: "support-topics",
          nuxt: true,
        },
        {
          text: "Öneri-Şikayet",
          disabled: false,
          href: "support-topics",
          nuxt: true,
        },
      ],
      tickets: [
        {
          ticketNo: 1,
          subject: "Modül 2 içerisindeki yazılım hatası",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 2,
          subject: "Proje editleme sorunu ile ilgili",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 3,
          subject: "KML Dosyası eklerken hata alıyorum",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 1,
          subject: "Modül 2 içerisindeki yazılım hatası",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 2,
          subject: "Proje editleme sorunu ile ilgili",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 3,
          subject: "KML Dosyası eklerken hata alıyorum",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 1,
          subject: "Modül 2 içerisindeki yazılım hatası",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 2,
          subject: "Proje editleme sorunu ile ilgili",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 3,
          subject: "KML Dosyası eklerken hata alıyorum",
          exp: "Lorem ipsum narem pipsum",
        },
      ],
      suggests: [
        {
          ticketNo: 1,
          subject: "Proje yönetim sistemi ekranı ile ilgili önerim",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 2,
          subject: "Destek taleplerinin daha hızlı sonuçlanması gerekiyor",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 3,
          subject: "Kullanıcı arayüzündeki ergonomik eksiklikler",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 1,
          subject: "Proje yönetim sistemi ekranı ile ilgili önerim",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 2,
          subject: "Destek taleplerinin daha hızlı sonuçlanması gerekiyor",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 3,
          subject: "Kullanıcı arayüzündeki ergonomik eksiklikler",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 1,
          subject: "Proje yönetim sistemi ekranı ile ilgili önerim",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 2,
          subject: "Destek taleplerinin daha hızlı sonuçlanması gerekiyor",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 3,
          subject: "Kullanıcı arayüzündeki ergonomik eksiklikler",
          exp: "Lorem ipsum narem pipsum",
        },
      ],
    };
  },
};
</script>

<style>
.header {
  font-size: 2.7em;
  color: #413f42;
  text-align: center;
}

.sub-header {
  font-size: 1.4em;
  color: #413f42;
}

.list-element {
  font-size: 0.95em;
  color: #413f42;
}

.list-element a {
  text-decoration: none;
  color: #7f8487;
}

.list-element a:hover {
  text-decoration: none;
  color: #413f42;
}

.items-section {
  background-color: #efefef;
  border-radius: 10px;
}
<<<<<<< HEAD

=======
>>>>>>> cd1b171768eed2bbf5fef2c5ca5637e6dad5e1b6
</style>
