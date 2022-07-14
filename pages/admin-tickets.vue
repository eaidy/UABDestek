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
    >
      <template #item.actions="{ item }">
        <v-icon @click="answerDialog = true" small>
          mdi-pencil
        </v-icon>
        <v-icon @click="closeTicketValidation = true" small> <!-- Kapat -->
          mdi-close
        </v-icon>
        <v-icon @click="deleteTicketValidation = true" small>  <!-- Sil -->
          mdi-delete
        </v-icon>
      </template>
    </v-data-table>

      <v-dialog v-model="answerDialog" :width="expandedWidth">
        <v-card>
          <v-card-title class="justify-center">
            Talep Oluştur
          </v-card-title>

          <v-divider></v-divider>
          <v-container>
            <v-row>
              <v-col class="vertical-rule" :class="{ bottomrule : expandedDialog }">
                <v-card-text class="mt-4">
                  <v-container>
                    <v-row>
                      <v-col cols="6" class="">
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
                    <v-row>
                      <v-col>
                        <v-text-field label="Konu" outlined class="mb-6"></v-text-field>
                      </v-col>
                    </v-row>
                    <v-row>
                      <v-col>
                        <v-textarea label="Açıklama" outlined></v-textarea>
                      </v-col>
                    </v-row>
                    <v-row>
                      <v-col>
                        <div class="d-flex mt-8">
                          <v-btn color="primary" @click="dialog = false"> Gönder </v-btn>
                          <v-btn
                            color="secondary"
                            text
                            @click="answerDialog = false"
                            class="ml-4"
                          >
                            İptal
                          </v-btn>
                          <v-spacer></v-spacer>
                          <div class="admin-ticket-expand-div">
                            <span v-if="!expandedDialog.stop" @click="expandedDialog = true" class="admin-ticket-expand">Detay >></span>
                            <span v-if="expandedDialog.stop" @click="expandedDialog = false" class="admin-ticket-expand">&lt&lt Kısalt</span>
                          </div>
                        </div>
                      </v-col>
                    </v-row>
                    <v-row>
                      <v-col>
                        <v-divider></v-divider>
                        <v-card-actions>
                          <v-spacer></v-spacer>
                          <div class="d-flex justify-space-between align-items-center w-100">
                            <div class="w-300" style="width: 300px;">
                              <v-file-input
                                accept="image/*"
                                label="Dosya Ekleyin"
                                style="width: 300px;"
                              ></v-file-input>
                            </div>
                          </div>
                        </v-card-actions>
                      </v-col>
                    </v-row>
                    <!-- Talep Süreci Diyaloğu -->
                    <v-row>
                      <v-col>
                        <v-card-text>
                          <v-container>
                            <v-row>
                              <v-col>
                                <h3>Talep Süreci</h3>
                              </v-col>
                            </v-row>
                            <v-row>
                              <v-col>
                                <v-container>
                                  <TicketHistoryPost v-for="post in posts" :key="post.id" :post="post" />
                                </v-container>
                              </v-col>
                            </v-row>
                          </v-container>
                        </v-card-text>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-card-text>
              </v-col> 

              <!-- Expanded kısım -->
              <v-col v-if="expandedDialog" :class="{ bottomrule : expandedDialog }">
                <v-card-text class="mt-4">
                  <v-container>
                    <v-row>
                      <v-col>
                        <v-textarea label="Admin Notları" outlined></v-textarea>
                      </v-col>
                    </v-row>
                    <v-row>
                      <v-col>
                        <v-subheader>
                          Etiket eklemek için, etiket ismini yazıp 'Enter' tuşuna basınız.
                        </v-subheader>
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
                    </v-row>
                    <!-- <v-row>
                      <v-col>
                        <v-subheader>
                          İlgili kişi eklemek için, kişinin ismini yazıp 'Enter' tuşuna basınız.
                        </v-subheader>
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
                    <v-row>
                      <v-col>
                        <v-subheader>İlgili Makaleleri İliştir</v-subheader>
                        <v-text-field
                          label="Arama"
                          outlined
                          v-model="ticketSearch"
                        >
                        </v-text-field>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-card-text> 
              </v-col>
            </v-row>

          </v-container>
          
        </v-card>
      </v-dialog>
  </v-container>
</template>

<script>
import TicketHistoryPost from '~/components/TicketHistoryPost.vue';
export default {
    data() {
        return {
            answerDialog: false,
            expandedDialog: false,
            ticketSearch: "",
            headers: [
                {
                    text: "Sıra",
                    align: "center",
                    sortable: true,
                    value: "queue",
                },
                { text: "Talep No.", value: "ticketno" },
                { text: "Tarih", value: "begindate" },
                { text: "Talep Sahibi", value: "ticketowner" },
                { text: "Kurumu", value: "institution" },
                { text: "Talep", value: "ticketsubject" },
                { text: "Sorumlu", value: "personincharge" },
                { text: "Onaylayan", value: "confirmer" },
                { text: "Durumu", value: "state" },
                { text: "Tarih", value: "enddate" },
                { text: "Actions", value: "actions", sortable: false }
            ],
            tickets: [
                {
                    queue: 1,
                    ticketno: "TIC1001",
                    begindate: "23.05.2022",
                    ticketowner: "Doruk Yormaz",
                    institution: "TCDD",
                    ticketsubject: "KML dosyası yükleyememe problemi",
                    personincharge: "Bensu Keşap",
                    confirmer: "Cem Karakuş",
                    state: "DOĞRU",
                    enddate: "23.05.2022"
                },
                {
                    queue: 2,
                    ticketno: "TIC2038",
                    begindate: "23.05.2022",
                    ticketowner: "Elif Atar",
                    institution: "TCDD",
                    ticketsubject: "Proje veri girememe problemi",
                    personincharge: "Bensu Keşap",
                    confirmer: "Cem Karakuş",
                    state: "DOĞRU",
                    enddate: "23.05.2022"
                },
                {
                    queue: 3,
                    ticketno: "TIC1587",
                    begindate: "23.05.2022",
                    ticketowner: "Önder Çelik",
                    institution: "TCDD",
                    ticketsubject: "Yeni yüklenici eklenmesi talebi",
                    personincharge: "Bensu Keşap",
                    confirmer: "Cem Karakuş",
                    state: "DOĞRU",
                    enddate: "23.05.2022"
                }
            ],
            posts: [
              { id: 1, exp: 'Açıklama 1', isAdmin: false},
              { id: 2, exp: 'Açıklama 2', isAdmin: true},
              { id: 3, exp: 'Açıklama 3', isAdmin: false},
              { id: 4, exp: 'Açıklama 3', isAdmin: false}
            ],
            modules: [
                "Modül 1",
                "Modül 2",
                "Modül 3"
            ],
            ticketTypes: [
                "Şifre Değiştirme",
                "Destek-Talep",
                "Öneri-Şikayet"
            ],
            tags: [],
            people: [],
            temp: {
                tag: "",
                person: ""
            }
        };
    },
    computed: {
        expandedWidth() {
            return this.expandedDialog ? 1000 : 800;
        }
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
        }
    },
    components: { TicketHistoryPost }
};
</script>

<style lang="scss" scoped>
.v-text-field.v-text-field--enclosed .v-text-field__details {
  display: none;
}

.admin-ticket-expand-div {
  display: flex;
  align-items:flex-end;
}

.admin-ticket-expand {
  font-size: 1.1em;
}

.admin-ticket-expand:hover {
  cursor: pointer;
  color: #7F8487;
}

.vertical-rule {
  border-right: 1px solid;
  border-color: rgba(0, 0, 0, 0.12);
}

.tag {
  border-radius: 5px;
  border-bottom: solid 1px gray;
  border-left: solid 1px gray;
  margin-right: 4px;
  padding: 4px;
}

.tags {
  padding-left: 4px;
}

.process-header {
  border-bottom: 1px solid;
  border-color: rgba(0, 0, 0, 0.12);

}

.bottomrule {
  border-bottom: 1px solid;
  border-color: rgba(0, 0, 0, 0.12);
}
</style>
