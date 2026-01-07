<script setup lang="ts">
import { ref } from "vue";
import Separator from "./ui/separator/Separator.vue";
import MainLogo from "@/components/ui/navigation-menu/MainLogo.vue";
import ImprintOverlay from "@/components/ImprintOverlay.vue";
import PrivacyPolicyOverlay from "./PrivacyPolicyOverlay.vue";

const showPrivacyPolicy = ref(false);
const showImprint = ref(false);
</script>

<template>
    <footer id="footer" class="container py-24 pb-16 sm:py-32 sm:pb-24">
        <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
            <div class="grid grid-cols-2 md:grid-cols-4 xl:grid-cols-6 gap-x-12 gap-y-8">
                <div class="col-span-full xl:col-span-2">
                    <main-logo></main-logo>
                </div>

                <div class="flex flex-col gap-2">
                    <h3 class="font-bold text-lg">Unternehmen</h3>
                    <div>
                        <a
                            href="#"
                            class="opacity-60 hover:opacity-100 cursor-pointer"
                            @click.prevent="showImprint = true"
                        >
                            Impressum
                        </a>
                        <ImprintOverlay v-if="showImprint" @close="showImprint = false" />
                    </div>

                    <div>
                        <a
                            href="#"
                            class="opacity-60 hover:opacity-100 cursor-pointer"
                            @click.prevent="showPrivacyPolicy = true"
                        >
                            Datenschutz
                        </a>
                        <PrivacyPolicyOverlay
                            v-if="showPrivacyPolicy"
                            @close="showPrivacyPolicy = false"
                        />
                    </div>
                </div>

                <div class="flex flex-col gap-2">
                    <h3 class="font-bold text-lg">Socials</h3>
                    <div>
                        <a
                            href="https://www.instagram.com/coupling.media/"
                            class="opacity-60 hover:opacity-100"
                        >
                            Instagram
                        </a>
                    </div>

                    <div>
                        <a
                            href="https://www.linkedin.com/company/couplingmedia/"
                            class="opacity-60 hover:opacity-100"
                        >
                            LinkedIn
                        </a>
                    </div>

                    <div>
                        <a href="https://coupling.media" class="opacity-60 hover:opacity-100">
                            Website
                        </a>
                    </div>
                </div>
            </div>

            <Separator class="my-6" />
            <section className="">
                <h3 class="">
                    &copy;
                    <a
                        target="_blank"
                        href="https://coupling.media"
                        className="text-primary transition-all border-primary hover:border-b-2"
                    >
                        coupling media GmbH
                    </a>
                </h3>
            </section>
        </div>
    </footer>
</template>
