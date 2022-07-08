<template>
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

        <v-row class="items-section elevation-2">
            <v-col col="6">
                <div>
                    <div class="sub-header ml-3">
                        <v-icon class="mb-1">mdi-file-document-check</v-icon> Destek Talepleri
                    </div>
                    <div class="ml-6 mt-2">
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
                    <div class="sub-header ml-3">
                        <v-icon class="mb-1">mdi-file-document-edit</v-icon> Öneri ve Şikayetler
                    </div>
                    <div class="ml-6 mt-2">
                        <div v-for="suggest in suggests" :key="suggest.id">
                            <v-icon small>mdi-pencil</v-icon><span class="ml-2 list-element"><a href="/support-topics">{{ suggest.subject }}</a></span>
                        </div>
                    </div>
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>

export default {
    data () {
        return {
            links: [
                {
                    text: 'Destek-Talep',
                    disabled: false,
                    href: 'support-topics',
                    nuxt: true
                },
                {
                    text: 'Öneri-Şikayet',
                    disabled: false,
                    href: 'support-topics',
                    nuxt: true
                }
            ],
            tickets: [
                {
                    ticketNo: 1,
                    subject: 'Modül 2 içerisindeki yazılım hatası',
                    exp: 'Lorem ipsum narem pipsum',
                },
                {
                    ticketNo: 2,
                    subject: 'Proje editleme sorunu ile ilgili',
                    exp: 'Lorem ipsum narem pipsum'
                },
                {
                    ticketNo: 3,
                    subject: 'KML Dosyası eklerken hata alıyorum',
                    exp: 'Lorem ipsum narem pipsum'
                }
            ],
            suggests: [
                {
                    ticketNo: 1,
                    subject: 'Proje yönetim sistemi ekranı ile ilgili önerim',
                    exp: 'Lorem ipsum narem pipsum'
                },
                {
                    ticketNo: 2,
                    subject: 'Destek taleplerinin daha hızlı sonuçlanması gerekiyor',
                    exp: 'Lorem ipsum narem pipsum'
                },
                {
                    ticketNo: 3,
                    subject: 'Kullanıcı arayüzündeki ergonomik eksiklikler',
                    exp: 'Lorem ipsum narem pipsum'
                }
            ]
        }
    }
}
</script>

<style>

.header {
    font-size: 2.7em;
    color: #413F42;
    text-align: center;
}

.sub-header {
    font-size: 1.4em;
    color: #413F42;
}

.list-element {
    font-size: 0.95em;
    color: #413F42;
}

.list-element a {
    text-decoration: none;
    color:#7F8487;
}

.list-element a:hover {
    text-decoration: none;
    color:#413F42;
}

.items-section {
    background-color: #EFEFEF;
    border-radius: 10px;
}

</style>