<script setup>
</script>

<template>
    <header>
        <div class="container">
            <div class="header">
                <img alt="Vue logo" class="logo" src="@/assets/img/logo.svg" width="30" height="30" />
                <nav>
                    <RouterLink to="/" class="btn btn-primary">Home</RouterLink>
                    <RouterLink to="/about" class="btn btn-primary">About</RouterLink>
                </nav>
            </div>
        </div>
    </header>
</template>

<style scoped lang="scss">
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    padding: 10px 0;
    a {
        margin-left: 10px;
    }
}
</style>
