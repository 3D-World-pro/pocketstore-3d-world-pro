<script setup>
import PocketBase from 'pocketbase';
import { usePocketbaseStore } from '~/stores/pocketbase';
import { useBreadcrumbStore } from '~/stores/breadcrumb';

const store = usePocketbaseStore();
const { url } = storeToRefs(store);
const pb = new PocketBase(url.value);
const category = ref({});
const products = ref([]);

onMounted(async () => {
    category.value = await pb.collection('categories').getFirstListItem('name="Welcome"', {
        expand: 'products',
        sort: 'products.created'
    });
    products.value = category.value.expand.products;
});

const storeBreadcrumb = useBreadcrumbStore();
storeBreadcrumb.clear();
</script>

<template>
    <section class="page">
        <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3">
            <div class="col-span-6">
                <div class="hero bg-base-200 rounded-lg">
                    <div class="hero-content flex-col lg:flex-row">
                        <img src="/3d-world-banner.jpg" class="max-w-lg rounded-lg shadow-2xl">
                        <div>
                            <h1 class="text-5xl font-bold">
                                Explore the <span class="text-primary">3D World</span>
                            </h1>
                            <p class="py-6 text-lg">
                                Unlock the power of a <span class="font-semibold">Pro Domain</span> for your 3D
                                universe.
                                Seamless experiences, infinite possibilities.
                            </p>
                            <a href="/get-started" class="btn btn-primary">
                                Get Started
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            <div v-for="product in products" :key="product.id" class="col-span-6 md:col-span-2 py-3">
                <CatalogProductCard :identifier="product.id" />
            </div>
        </div>
    </section>
</template>