<template>
    <div class="home">
        <h1>Home page</h1>
    </div>
</template>

<script>
import { useMeta } from 'vue-meta'

export default {
    name: "HomeView",
    setup() {
        useMeta({
            title: 'Home page',
            description: "Ceci est une description de la page d'accueil",
            htmlAttrs: { lang: 'fr', amp: true }
        })
    }
}
</script>

<style scoped lang=scss>
</style>