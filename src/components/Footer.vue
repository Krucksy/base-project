<script setup>
import Copyrights from '@/components/Copyrights.vue'
</script>

<template>
    <footer>
        <div class="container">
            <div class="footer">
                <img alt="Vue logo" class="logo" src="@/assets/img/logo.svg" width="30" height="30" />
                <nav>
                    <RouterLink to="/" class="btn btn-primary">Home</RouterLink>
                    <RouterLink to="/about" class="btn btn-primary">About</RouterLink>
                </nav>
            </div>
        </div>
    </footer>
    <Copyrights></Copyrights>
</template>

<style scoped lang="scss">
footer {
    background-color: rgb(51, 51, 51);
}
.footer {
    display: flex;
    width: 100%;
    padding: 10px 0;
    .logo {
        margin-right: 20px;
    }
    nav {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        a {
            margin-bottom: 10px;
        }
    }
}
</style>
