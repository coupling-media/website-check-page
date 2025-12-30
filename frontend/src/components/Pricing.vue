<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Check } from "lucide-vue-next";
import {Badge} from "@/components/ui/badge";

enum PopularPlan {
  NO = 0,
  YES = 1,
}

interface PlanProps {
  title: string;
  popular: PopularPlan;
  price: number;
  description: string;
  buttonText: string;
  benefitList: string[];
}

const plans: PlanProps[] = [
  /*
  {
    title: "SEO und SEA Optimierung",
    popular: 0,
    price: 599,
    description:
      "Für Unternehmen, die gezielt ihre Sichtbarkeit und Werbekosten verbessern wollen.",
    buttonText: "Optimierung anfragen",
    benefitList: [
      "Technische SEO-Analyse",
      "Keyword- & Wettbewerbsanalyse",
      "Meta-Daten & Content-Struktur",
      "Google-Ads-Audit & Kampagnenoptimierung",
      "Budgeteffizienz & Zielgruppen-Check",
      "Individueller Maßnahmenplan"
    ],
  },
  */
  {
    title: "Kostenloser Website-Check",
    popular: 1,
    price: 0,
    description:
        "Erhalten Sie einen schnellen, transparenten Überblick über den Status Ihrer Website.",
    buttonText: "Jetzt kostenlos überprüfen lassen",
    benefitList: [
    "Sichtbarkeitsanalyse (SEO-Grundwerte)",
      "Erste SEA-Potentialeinschätzung",
      "UX & Design-Check",
      "Barrierefreiheits-Bewertung",
      "Auffällige optische & strukturelle Fehler",
      "Kurzreport mit Prioritäten"
    ],
  } /*,
  {
    title: "Komplette Web-Optimierung",
    popular: 0,
    price: 1999,
    description:
      "Die ganzheitliche Lösung für maximale Performance in Technik, Design und Conversion.",
    buttonText: "Projekt starten",
    benefitList: [
      "Vollständiges Technik-Audit (Core Web Vitals, Struktur, Fehlerquellen)",
      "UX- & Conversion-Analyse",
      "Content-Optimierung & Seitenarchitektur",
      "Performance-Check & Ladezeitverbesserung",
      "SEO + SEA + Tracking-Optimierung",
      "Individuelle Strategie inkl. Roadmap & Workshop"
    ],
  }, 
  */
];
</script>

<template>
  <section class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Pricing
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Für jeden die richtige Lösung
    </h2>

    <h3
      class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground pb-14"
    >
      Damit Sie genau das bekommen was Ihr Unternehmen benötigt.
    </h3>

    <div class="flex items-center justify-center">
      <Card
        v-for="{
          title,
          popular,
          price,
          description,
          buttonText,
          benefitList,
        } in plans"
        :key="title"
        :class="{
          'drop-shadow-xl shadow-black/10 dark:shadow-white/10 border-[1.5px] border-primary lg:scale-[1.1]':
            popular === PopularPlan?.YES,
        }"
      >
        <CardHeader>
          <CardTitle class="pb-2">
            {{ title }}
          </CardTitle>

          <CardDescription class="pb-4">{{ description }}</CardDescription>

          <div>
            <span class="text-muted-foreground">ab </span>
            <span class="text-3xl font-bold">${{ price }}</span>
          </div>
        </CardHeader>

        <CardContent class="flex">
          <div class="space-y-4">
            <span
              v-for="benefit in benefitList"
              :key="benefit"
              class="flex"
            >
              <Check class="text-primary mr-2" />
              <h3>{{ benefit }}</h3>
            </span>
          </div>
        </CardContent>

        <CardFooter>
          <Button
            :variant="popular === PopularPlan?.NO ? 'secondary' : 'default'"
            class="w-full"
          >
            {{ buttonText }}
          </Button>
        </CardFooter>
        <Badge
            v-if="popular === PopularPlan.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
        >Meistgebucht</Badge
        >
      </Card>
    </div>
  </section>
</template>
