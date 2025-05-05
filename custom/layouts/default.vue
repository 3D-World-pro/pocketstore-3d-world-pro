<template>
    <section class="min-h-screen -z-2">
        <header class="mx-auto max-w-6xl">
            <Header />
        </header>
        <main class="mx-auto max-w-6xl min-h-screen px-3">
            <Messages />
            <Breadcrumb />
            <CookieBanner />
            <slot />
        </main>
        <footer class="">
            <Footer />
        </footer>
        <Particles />
    </section>
</template>
<script setup lang="ts">
import '../main.css';
import tracking from '~/util/tracking';

import Footer from '~/components/Footer.vue';
import Header from '~/components/Header.vue';
import Particles from '../components/Particles.vue';

onMounted(() => {
    tracking.trackPage()
});
</script>