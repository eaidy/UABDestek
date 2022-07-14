<template>
    <v-row>
        <v-col class="px-0">
            <div v-if="!post.isAdmin" class="post post-client pb-1 mr-12">
                <div>
                    <span>{{ post.exp }}</span>
                </div>
                <div class="post-info-box justify-end">
                    <span>Kullanıcı &nbsp</span>|<span>&nbsp{{ post.date }}</span>
                </div>
            </div>
            <div v-else class="post post-admin pb-1 ml-12">
                <div>
                    <span>{{ post.exp }}</span>
                </div>
                <div class="post-info-box justify-end">
                    <span>Destek Ekibi &nbsp</span>|<span>&nbsp{{ post.date }}</span>
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
    font-size: 0.7em;
    margin-top: 4px;
}
</style>