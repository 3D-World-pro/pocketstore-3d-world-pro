<script setup>
import { useBreadcrumbStore } from '~/stores/breadcrumb';
import { faEdit, faUser, faStar, faCheck } from '@fortawesome/free-solid-svg-icons'
import { FontAwesomeIcon as Fa } from '@fortawesome/vue-fontawesome'
const storeBreadcrumb = useBreadcrumbStore();
storeBreadcrumb.clear();</script>

<template>
    <section class="page">
        <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3">
            <HomepageHero />
            <div class="col-span-6">
                <div class="grid grid-cols-6 gap-3 my-12 bg-white rounded-lg py-12 border-[#44cfb3] border-2">
                    <div class="col-span-6 md:col-span-2 text-center">
                        <section class="rounded-lg flex justify-center">
                            <Fa :icon="faUser" color="#44cfb3" size="4x" />
                        </section>
                        <h2 class="font-bold text-black">Von Kunden</h2>
                        <p class="text-sm text-center">empfohlen</p>
                    </div>
                    <div class="col-span-6 md:col-span-2 text-center">
                        <section class="rounded-lg flex justify-center">
                            <Fa :icon="faStar" color="#44cfb3" size="4x" />
                        </section>
                        <h2 class="font-bold text-black mt-3">Top Bewertungen</h2>
                    </div>
                    <div class="col-span-6 md:col-span-2 text-center">
                        <section class="rounded-lg flex justify-center">
                            <Fa :icon="faCheck" color="#44cfb3" size="4x" />
                        </section>
                        <h2 class="font-bold text-black">Erfolgreich getestet</h2>
                    </div>
                </div>
                <div class="grid grid-cols-6 gap-3 my-12 bg-white rounded-lg py-12 border-[#44cfb3] border-2">
                    <div class="col-span-6 md:col-span-2 text-center">
                        <section class="rounded-lg flex justify-center">
                            <Fa :icon="faUser" color="#44cfb3" size="4x" />
                        </section>
                        <h2 class="font-bold text-black">Hallo Welt</h2>
                    </div>
                    <div class="col-span-6 md:col-span-2 text-center">
                        <section class="rounded-lg flex justify-center">
                            <Fa :icon="faUser" color="#44cfb3" size="4x" />
                        </section>
                        <h2 class="font-bold text-black">Hallo Welt</h2>
                    </div>
                    <div class="col-span-6 md:col-span-2 text-center">
                        <section class="rounded-lg flex justify-center">
                            <Fa :icon="faUser" color="#44cfb3" size="4x" />
                        </section>
                        <h2 class="font-bold text-black">Hallo Welt</h2>
                    </div>
                </div>
            </div>
            <CatalogProductGrid identifier="bowling" />
        </div>
    </section>
</template>
