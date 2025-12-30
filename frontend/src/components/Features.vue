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
  Wrench,
  TimerReset,
  CodeXml,
  FilePenLine,
  Proportions,
  Search
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "wrench",
    title: "Technische SEO-Grundlagen",
    description:
      "Wir prüfen, ob Ihre Website für Suchmaschinen technisch sauber erreichbar und indexierbar ist.",
  },
  {
    icon: "timerReset",
    title: "Ladezeit & Performance",
    description:
      "Analyse der Website-Geschwindigkeit als wichtiger Faktor für Nutzererlebnis und SEO.",
  },
  {
    icon: "codeXml",
    title: "OnPage-Struktur & Meta-Daten",
    description:
      "Bewertung der Seitenstruktur und der wichtigsten SEO-Elemente.",
  },
  {
    icon: "filePenLine",
    title: "Content-Qualität & Verständlichkeit",
    description:
      "Wir prüfen, ob Inhalte klar, relevant und suchmaschinenfreundlich aufgebaut sind.",
  },
  {
    icon: "proportions",
    title: "Nutzerführung & User Experience",
    description:
      "Analyse, wie intuitiv Nutzer durch die Website geführt werden.",
  },
  {
    icon: "search",
    title: "Sichtbarkeit & Grund-SEO-Status",
    description:
      "Einordnung des aktuellen SEO-Status auf Basis von SISTRIX-Daten.",
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
  | typeof Wrench
  | typeof TimerReset
  | typeof CodeXml
  | typeof FilePenLine
  | typeof Proportions
  | typeof Search
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
  wrench: Wrench,
  timerReset: TimerReset,
  codeXml: CodeXml,
  filePenLine: FilePenLine,
  proportions: Proportions,
  search: Search
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Analyse
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Was prüfen wir?
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      Jede Website ist anders. Deshalb ist auch unsere Analyse individuell. Statt automatisierter Reports erhalten Sie konkrete, priorisierte Empfehlungen von erfahrenen Marketing-Experten.
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
