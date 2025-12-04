<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "Mobile Optimierung",
    description:
      "Ihre Website wird auf allen Geräten geprüft - damit Nutzer unterwegs keine Barrieren erleben und Google Sie besser rankt.",
  },
  {
    icon: "badgeCheck",
    title: "Klare Datenbasis",
    description:
      "Wir bieten Transparenz statt Vermutungen: Sie erhalten verständliche Auswertungen mit konkreten Handlungsempfehlungen.",
  },
  {
    icon: "goal",
    title: "Zielgerichtete Inhalte",
    description:
      "Wir analysieren Struktur, Texte und Nutzerführung, damit Ihre Botschaften wirklich ankommen und Conversions steigen.",
  },
  {
    icon: "pictureInPicture",
    title: "Visuelle Qualität",
    description:
      "Design, Layout und Bildoptimierung im Detail geprüft - für einen professionellen Eindruck und kürzere Ladezeiten.",
  },
  {
    icon: "mousePointerClick",
    title: "Optimierte Call-to-Actions",
    description:
      "Wir bewerten Aufbau und Positionierung Ihrer CTAs, damit Besucher wissen, welchen nächsten Schritt sie gehen sollen.",
  },
  {
    icon: "newspaper",
    title: "Starke Struktur & Headlines",
    description:
      "Ihre Seitenarchitektur und Überschriften werden auf Verständlichkeit, SEO-Relevanz und Nutzerintention ausgerichtet.",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Features
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Was uns einzigartig macht
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Ein Website-Check ist mehr als ein schneller Blick auf Design oder Keywords. Wir analysieren Ihre Seite ganzheitlich - datenbasiert, strukturiert und mit einem klaren Fokus auf echte Performance.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
