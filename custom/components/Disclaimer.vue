<template>
    <div class="alert alert-error text-white mx-3 md:mx-auto">
        <Fa :icon="faCircleInfo" />
        <p class="text-sm">
            Dies ist ein Demo Store von PocketStore.io. Docs and Getting Started ->
            <a href="https://www.PocketStore.io" class="text-blue-600" target="_blank"
                rel="noopener noreferrer">PocketStore.io</a>
        </p>
    </div>
</template>

<script setup lang="ts">
import { faCircleInfo } from '@fortawesome/free-solid-svg-icons';
</script>