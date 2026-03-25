<script setup lang="ts">
import { ref } from "vue";
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";
import SignupOverlay from "@/components/SignupOverlay.vue";
import { Button } from "@/components/ui/button";
import { ArrowRight } from "lucide-vue-next";
import CardButton from "./ui/card/CardButton.vue";

const showSignup = ref(false);

interface HowItWorksProps {
    badgeTitle: string;
    title: string;
    description: string;
    image: string;
    glowColor: string;
    ctaButton: Boolean;
}

const HowItWorksList: HowItWorksProps[] = [
    {
        badgeTitle: "Anfrage",
        title: "Website kostenlos anmelden",
        description:
            "Sie senden uns Ihre Website-URL und ein paar Angaben zu Ihrem Unternehmen - der Check ist für Sie unverbindlich.",
        image: "max-1.svg",
        glowColor: "#EE720326",
        ctaButton: true,
    },
    {
        badgeTitle: "Analyse",
        title: "Technik, SEO & UX prüfen",
        description:
            "Unsere Marketing-Experten prüfen Ihre Website manuell anhand definierter Kriterien - keine automatisierten Tool-Reports.",
        image: "max-2.svg",
        glowColor: "#1873AA26",
        ctaButton: false,
    },
    {
        badgeTitle: "Insights",
        title: "Strukturierte Auswertung",
        description:
            "Die Auswertung erfolgt persönlich - entweder in einem Online-Termin oder vor Ort. Gemeinsam gehen wir die Ergebnisse durch und beantworten Ihre Fragen.",
        image: "max-3.svg",
        glowColor: "#B31EB126",
        ctaButton: false,
    },
    {
        badgeTitle: "Umsetzung",
        title: "Optimierungen gezielt realisieren",
        description:
            "Auf Wunsch unterstützen wir Sie oder Ihr Team bei der Umsetzung - von schnellen Anpassungen bis zur umfassenden Optimierung.",
        image: "max-4.svg",
        glowColor: "#6AAF1826",
        ctaButton: false,
    },
];
</script>

<template>
    <section id="how-it-works" class="container py-24 sm:py-32">
        <div class="text-center mb-8">
            <h2 class="text-lg text-primary text-center mb-2 tracking-wider">So einfach geht's</h2>

            <h2 class="text-3xl md:text-4xl text-center font-bold">
                Ihr Website-Check in 4 Schritten
            </h2>
        </div>

        <div class="lg:w-[80%] mx-auto relative">
            <div
                v-for="(
                    { badgeTitle, title, description, image, glowColor, ctaButton }, index
                ) in HowItWorksList"
                :key="title"
                :class="[
                    'flex flex-col lg:flex-row mb-8 items-center',
                    { 'lg:flex-row-reverse': index % 2 !== 0 }
                    ]"
            >
                <Card class="h-full bg-transparent border-0 shadow-none">
                    <CardHeader class="text-center lg:text-left">
                        <div class="pb-4">
                            <Badge>{{ badgeTitle }}</Badge>
                        </div>

                        <CardTitle class="text-center lg:text-left">
                            {{ title }}
                        </CardTitle>
                    </CardHeader>

                    <CardContent class="text-muted-foreground w-[80%] text-center lg:text-left mx-auto lg:mx-0">
                        {{ description }}
                    </CardContent>

                    <CardButton class="flex justify-center lg:justify-start">
                        <Button
                            v-if="ctaButton"
                            class="w-5/6 md:w-1/4 font-bold group/arrow"
                            @click="showSignup = true"
                        >
                            Jetzt anmelden
                            <ArrowRight
                                class="size-5 ml-2 group-hover/arrow:translate-x-1 transition-transform"
                            />
                        </Button>
                    </CardButton>

                    <!-- Overlay anzeigen -->
                    <SignupOverlay v-if="showSignup" @close="showSignup = false" />
                </Card>

                <img
                    :src="image"
                    :alt="`Image describing ${title} `"
                    class="h-[180px] lg:h-[240px] w-auto flex-none mx-auto mt-6 lg:mt-0"
                />
                <div
                    :class="[
                        '-z-10 absolute right-0 w-44 h-72  lg:w-64 lg:h-80 rounded-full blur-3xl',
                        {
                            'left-0': index % 2 !== 0,
                        },
                    ]"
                    :style="{ backgroundColor: glowColor }"
                ></div>
            </div>
        </div>
    </section>
</template>
