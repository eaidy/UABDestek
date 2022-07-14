<template>
  <div>
    <section class="search-bg">
      <v-container>
        <v-row class="ma-4">
            <v-col cols="12">
                <div class="header">
                    Uygun Başlıklar
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

        <v-row class="items-section">
            <v-col col="6">
                <div>
                    <div class="sub-header ml-3 mb-3">
                        <v-icon class="mb-1">mdi-file-document-check</v-icon> Destek Talepleri
                    </div>
                    <v-divider></v-divider>
                    <div class="ml-6 mt-4 pa-1">
                        <div v-for="ticket in tickets" :key="ticket.id" class="ma-1 pa-1 topic">
                          <div class="pa-1 ml-1">
                            <v-icon small>mdi-pencil</v-icon>
                            <span class="ml-2 list-element" @click="showTicket(ticket)">
                              {{ ticket.subject }}
                            </span>
                          </div>
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
                    <div class="ml-6 mt-4 pa-1">
                        <div v-for="suggest in suggests" :key="suggest.id" class="ma-1 pa-1 topic">
                          <div class="pa-1 ml-1">
                            <v-icon small>mdi-pencil</v-icon>
                            <span 
                              class="ml-2 list-element"
                              @click="showTicket(suggest)"
                            >
                            {{ suggest.subject }}
                            </span>
                          </div>  
                        </div>
                    </div>
                </div>
            </v-col>
        </v-row>
        <v-dialog
          v-model="ticketDialog"
          max-width="800"
        >
          <v-card>
            <v-card-title class="text-h5 justify-center">
              {{ ticketBuffer.subject}} - İlgili Makale
            </v-card-title>
            <v-divider></v-divider>
            <v-card-text>
              <div class="related-article pa-3 ma-3">
                <p>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean vitae erat odio. Suspendisse eget elit sit amet ex lacinia pulvinar. Nam eget accumsan ante. Etiam vitae congue ligula. Nulla malesuada tellus a nisl pharetra, ut pretium ipsum blandit. Fusce ultricies ac nunc ut scelerisque. Morbi quis gravida erat, quis facilisis tortor. Suspendisse vitae odio turpis. Donec viverra elit metus, a vehicula libero malesuada quis. Maecenas a nunc pulvinar, hendrerit augue et, scelerisque enim. Morbi vestibulum quam at nisi imperdiet varius. Ut convallis auctor neque, id mattis elit condimentum nec. Nulla vitae tincidunt nisi. Sed bibendum sagittis nisi id ultrices. Aenean.
                </p>
              </div>
            </v-card-text>

          </v-card>
        </v-dialog>
      </v-container>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ticketDialog: false,
      ticketBuffer: {},
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
          ticketNo: 4,
          subject: "Modül 2 içerisindeki yazılım hatası",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 5,
          subject: "Proje editleme sorunu ile ilgili",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 6,
          subject: "KML Dosyası eklerken hata alıyorum",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 7,
          subject: "Modül 2 içerisindeki yazılım hatası",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 8,
          subject: "Proje editleme sorunu ile ilgili",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 9,
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
          ticketNo: 4,
          subject: "Proje yönetim sistemi ekranı ile ilgili önerim",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 5,
          subject: "Destek taleplerinin daha hızlı sonuçlanması gerekiyor",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 6,
          subject: "Kullanıcı arayüzündeki ergonomik eksiklikler",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 7,
          subject: "Proje yönetim sistemi ekranı ile ilgili önerim",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 8,
          subject: "Destek taleplerinin daha hızlı sonuçlanması gerekiyor",
          exp: "Lorem ipsum narem pipsum",
        },
        {
          ticketNo: 9,
          subject: "Kullanıcı arayüzündeki ergonomik eksiklikler",
          exp: "Lorem ipsum narem pipsum",
        },
      ],
    };
  },

  methods: {
    showTicket (info) {
      this.ticketBuffer = info
      this.ticketDialog = true
    },
    closeTicket () {
      this.ticketBuffer = {},
      this.ticketDialog = false
    }
  }
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

.list-element{
  font-size: 0.95em;
  color: #413f42;
}

.list-element{
  text-decoration: none;
  color: #7f8487;
}

.list-element:hover {
  text-decoration: none;
  color: #413f42;
  cursor: pointer;
}

.items-section {
  background-color: #efefef;
  border-radius: 10px;
  margin: 0 10px;
}

.topic {
  border-radius: 5px;
}

.topic:hover {
  background-color: #DDDDDD;
}

.related-article {
  border: 1px solid gray;
  border-radius: 5px;
}

</style>
