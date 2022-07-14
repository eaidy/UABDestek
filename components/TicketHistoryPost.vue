<template>
    <v-row>
        <v-col class="px-0">
            <div v-if="!post.isAdmin" class="post post-client pb-1 mr-12">
                <div class="pl-1 mb-2">
                    <span>{{ post.exp }}</span>
                </div>
                <div class="post-info-box">
                    <div v-if="post.file" class="relevant-file">
                        <a><v-icon small>mdi-paperclip</v-icon>{{ post.file }}</a>
                    </div>
                    <div class="post-info">
                        <span>Kullanıcı &nbsp</span>|<span>&nbsp{{ post.date }}</span>
                    </div>
                </div>
            </div>
            <div v-else class="post post-admin pb-1 ml-12">
                <div class="pl-1 mb-2">
                    <span>{{ post.exp }}</span>
                </div>
                <div class="post-info-box">
                    <div v-if="post.file" class="relevant-file">
                        <a><v-icon small>mdi-paperclip</v-icon>{{ post.file }}</a>
                    </div>
                    <div class="post-info">
                        <span>Destek Ekibi &nbsp</span>|<span>&nbsp{{ post.date }}</span>
                    </div>
                </div>
            </div>
        </v-col>
        <!-- <v-col cols="6" class="pa-1">
            <div v-if="!post.isAdmin" class="post post-client pb-1">
                <div>
                    <span>{{ post.exp }}</span>
                </div>
                <div class="post-info-box justify-end">
                    <span>{{ post.date }}</span>
                </div>
            </div>
        </v-col>
        <v-col cols="6" class="pa-1">
            <div v-if="post.isAdmin" class="post post-admin pb-1">
                 <div>
                    <span>{{ post.exp }}</span>
                </div>
                <div class="post-info-box justify-end">
                    <span>{{ post.date }}</span>
                </div>
            </div>
        </v-col> -->
    </v-row>
</template>

<script>

export default {
    props: {
        post: null
    },
    data () {
        return {

        }
    }
}

</script>

<style scoped>

.post {
    border-radius: 5px;
    padding: 8px;
    background-color: #F7F5F2;
}

.post-info-box {
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    font-size: 0.7em;
    margin-top: 4px;
    height: 25px;
}

.relevant-file {
    align-self: flex-start;
}

.relevant-file a{
    text-decoration: none;
    color: #413F42;
}

.relevant-file a:hover {
    text-decoration: none;
    color: black;
}

.post-info {
    align-self: flex-end;
}
</style>