<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Wrench,
  ChartColumnDecreasing,
  ScanSearch,
  Clock,
  Sparkle,
  Tag,
  Paintbrush,
  Blocks,
  LineChart,
  Wallet,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "wrench",
    title: "Unentdeckte technische Fehler",
    description:
      "...die Ladezeiten verlängern und Rankings verschlechtern - ohne dass Sie es direkt sehen.",
  },
  {
    icon: "lineChart",
    title: "Schwache SEO-Performance",
    description:
      "...weil Suchmaschinen Ihre Seite schlechter bewerten und Sie dadurch weniger qualifizierte Besucher erreichen.",
  },
  {
    icon: "wallet",
    title: "Ineffiziente Nutzerführung",
    description:
      "...die dafür sorgt, dass Besucher abspringen, bevor sie Kontakt aufnehmen oder konvertieren.",
  },
  {
    icon: "scanSearch",
    title: "Blindflug bei Optimierungen",
    description:
      "...da Ihnen klare Daten fehlen, um zu verstehen, was funktioniert - und was Ihre Website wirklich kostet.",
  },
];

const iconMap: Record<
  string,
  | typeof Wrench
  | typeof ChartColumnDecreasing
  | typeof ScanSearch
  | typeof Clock
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Blocks
  | typeof LineChart
  | typeof Wallet
> = {
  wrench: Wrench,
  chartColumnDecreasing: ChartColumnDecreasing,
  scanSearch: ScanSearch,
  clock: Clock,
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  blocks: Blocks,
  lineChart: LineChart,
  wallet: Wallet,
};
</script>

<template>
  <section
    id="benefits"
    class="container py-24 sm:py-32"
  >
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-primary mb-2 tracking-wider">Problem</h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Warum Sie sich eine unoptimierte Website nicht leisten sollten
        </h2>
        <p class="text-l text-muted-foreground mb-8">
          Technische Fehler, schwache Inhalte oder langsame Ladezeiten schaden Ihrer Sichtbarkeit und Conversion Rate. Sie kosten messbar Geld - die häufigsten Probleme:        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <div class="flex justify-between">
              <component
                class="size-8 mb-6 text-primary"
                :is="iconMap[icon]"
              />

              <span
                class="text-4xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
