<script setup>
import { useBreadcrumbStore } from '~/stores/breadcrumb';

const storeBreadcrumb = useBreadcrumbStore();
storeBreadcrumb.clear();</script>

<template>
    <section class="page">
        <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3 bg-white rounded-lg">
            <HomepageHero />
            <CatalogProductGrid category-name="Welcome" />
        </div>
    </section>
</template>