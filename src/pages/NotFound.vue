<script>
export default {
    name: 'NotFound',
    methods: {
        goHome() {
            this.$router.push({ name: 'home' });
        }
    }
}
</script>

<template>
    <div class="container not-found-container">
        <h1 class="text-center title">404 NOT FOUND</h1>
        <div class="text-center">
            <a class="btn btn-primary" @click.prevent="goHome()">Torna alla Homepage</a>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.not-found-container{
    padding-top: 5rem;

    .title {
        font-size: 3rem;
    }
}
</style>