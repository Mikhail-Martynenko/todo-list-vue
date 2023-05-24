<template>
    <div id="app">
        <router-view />
    </div>
</template>

<script>
// import MainPage from "@/components/MainPage.vue";

export default {
    name: 'App',
    components: {
        // MainPage,
    },
}
</script>

<style>
#app {
    max-width: 960px;
    margin: 0 auto;
    padding: 20px;
}
</style>
