<script setup>
import { RouterLink, RouterView } from "vue-router";
import VueNav from '@/components/Nav.vue'
import VueFooter from '@/components/Footer.vue'
</script>

<template>
    <metainfo>
        <template v-slot:title="{ content }">
            {{
                content ? `${content} | TEST` : `TEST`
            }}
        </template>
    </metainfo>
    <VueNav></VueNav>
    <div class="container">
        <RouterView />
    </div>
    <VueFooter></VueFooter>
</template>

<style lang=scss>
@import "bootstrap/dist/css/bootstrap.min.css";
@import "@/assets/style/normalise.css";
</style>
