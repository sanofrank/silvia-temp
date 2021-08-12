<template>
    <v-row class="text-h1 mt-4"> 
        <v-col cols="12">
            <Title :title="title" :classes="'text-h1'"/>
        </v-col>
    </v-row>
</template>

<script>
export default {
    data() {
        return {
            title: 'Contact'
        }
    }
}
</script>