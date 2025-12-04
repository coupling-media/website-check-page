<script setup lang="ts">
import {
  Card,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Badge } from "@/components/ui/badge";

enum ProService {
  YES = 1,
  NO = 0,
}

interface ServiceProps {
  title: string;
  pro: ProService;
  description: string;
}

const serviceList: ServiceProps[] = [
  {
    title: "Technischer Website-Check",
    description:
      "Wir prüfen Ladezeiten, Core Web Vitals, Fehlerquellen und technische SEO-Bremsen Ihrer Seite im Detail.",
    pro: 0,
  },
  {
    title: "Content- & Struktur-Analyse",
    description:
      "Wir bewerten Texte, Navigation und Nutzerführung – damit Ihre Inhalte verständlich sind und Besucher gezielt leiten.",
    pro: 0,
  },
  {
    title: "Conversion-Potenzial Analyse",
    description: "Wir identifizieren Schwachstellen in CTAs, Pagespeed, Layout und Funnel, die Conversions ausbremsen.",
    pro: 0,
  },
  {
    title: "SEO-Optimierung",
    description: "Wir decken Ranking-Probleme auf, analysieren Keywords und zeigen, wie Sie langfristig bessere Sichtbarkeit erreichen.",
    pro: 1,
  },
];
</script>

<template>
  <section
    id="services"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Services
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Verbessern Sie die Leistung Ihrer Website
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Von technischer Analyse bis Content-Optimierung - wir liefern klare Einsichten und konkrete Maßnahmen, um Ihre Website erfolgreicher zu machen.
    </h3>
    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4"></div>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[60%] mx-auto"
    >
      <div
        v-for="{ title, description, pro } in serviceList"
        :key="title"
      >
        <Card class="bg-muted/60 dark:bg-card h-full relative">
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
          </CardHeader>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
        </Card>
      </div>
    </div>
  </section>
</template>
