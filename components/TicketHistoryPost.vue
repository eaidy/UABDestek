<template>
    <v-row>
        <v-col cols="6">
            <div v-if="!post.isAdmin" class="post post-client ml-2">
                <span>{{ post.exp }}</span>
            </div>
        </v-col>
        <v-col cols="6">
            <div v-if="post.isAdmin" class="post post-admin mr-2">
                <span>{{ post.exp }}</span>
            </div>
        </v-col>
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
    border: 1px solid gray;
    border-radius: 5px;
    padding: 5px;
}

</style>