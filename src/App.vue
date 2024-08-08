<script setup>
    import Header from './components/Header.vue'
    import Home from './components/Home.vue'
    import Content from './components/Content.vue'
    import Footer from './components/Footer.vue'
</script>

<template>
    <Header />
    <main class="bg-light bg-gradient">
        <Home />
        <Content />
    </main>
    <Footer />
</template>

<style scoped>
    main {
        width: 100%;
    }
</style>
