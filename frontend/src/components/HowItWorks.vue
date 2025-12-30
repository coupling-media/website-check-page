<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";

interface HowItWorksProps {
  badgeTitle: string;
  title: string;
  description: string;
  image: string;
}

const HowItWorksList: HowItWorksProps[] = [
  {
    badgeTitle: "Anfrage",
    title: "Website kostenlos anmelden",
    description:
      "Sie senden uns Ihre Website-URL und ein paar Angaben zu Ihrem Unternehmen - der Check ist für Sie unverbindlich.",
    image: "max-1.svg",
  },
  {
    badgeTitle: "Analyse",
    title: "Technik, SEO & UX prüfen",
    description:
      "Unsere Marketing-Experten prüfen Ihre Website manuell anhand definierter Kriterien - keine automatisierten Tool-Reports.",
    image: "max-2.svg",
  },
  {
    badgeTitle: "Insights",
    title: "Strukturierte Auswertung",
    description:
      "Die Auswertung erfolgt persönlich - entweder in einem Online-Termin oder vor Ort. Gemeinsam gehen wir die Ergebnisse durch und beantworten Ihre Fragen.",
    image: "pacheco.png",
  },
  {
    badgeTitle: "Umsetzung",
    title: "Optimierungen gezielt realisieren",
    description:
      "Auf Wunsch unterstützen wir Sie oder Ihr Team bei der Umsetzung - von schnellen Anpassungen bis zur umfassenden Optimierung.",
    image: "gamestation.png",
  },
];
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        How It Works
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Ihr Website-Check in 4 Schritten
      </h2>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="(
          { badgeTitle, title, description, image }, index
        ) in HowItWorksList"
        :key="title"
        :class="[
          'flex mb-8 items-center',
          { ' flex-row-reverse': index % 2 !== 0 },
        ]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <div class="pb-4">
              <Badge>{{ badgeTitle }}</Badge>
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground w-[80%]">
            {{ description }}
          </CardContent>
        </Card>

        <img
          :src="image"
          :alt="`Image describing ${title} `"
          class="w-[150px] md:w-[150px] lg:w-[300px] mx-auto p-12"
        />
        <div
          :class="[
            '-z-10 absolute right-0 w-44 h-72  lg:w-64 lg:h-80 rounded-full bg-primary/15 dark:bg-primary/10 blur-3xl',
            {
              'left-0': index % 2 !== 0,
            },
          ]"
        ></div>
      </div>
    </div>
  </section>
</template>
