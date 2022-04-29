<template>
    <div class="notFound">
        <h1>404 page</h1>
    </div>
</template>

<script>
import { useMeta } from 'vue-meta'

export default {
    name: "404View",
    setup() {
        useMeta({
            title: 'Page not Found',
            description: "Ceci est une description de la page 404",
            htmlAttrs: { lang: 'fr', amp: true }
        })
    }
}
</script>

<style scoped lang=scss>
</style>