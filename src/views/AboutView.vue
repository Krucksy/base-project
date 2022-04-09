<template>
    <div class="about">
        <h1>About page</h1>
    </div>
</template>

<script>
import { useMeta } from 'vue-meta'

export default {
    name: "AboutView",
    setup() {
        useMeta({
            title: 'About page',
            description: 'Ceci est une description de la page about',
            htmlAttrs: { lang: 'fr', amp: true }
        })
    }
}
</script>

<style scoped lang=scss>
</style>