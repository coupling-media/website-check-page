<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
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
    icon: "clock",
    title: "Zeitverlust",
    description:
      "...durch Kontaktversuche mit falschen oder nicht mehr aktiven Adressen",
  },
  {
    icon: "lineChart",
    title: "Sinkende Conversion Rates",
    description:
      "...die einen Erfolg vorgaukeln, obwohl die Datenbasis das eigentliche Problem ist.",
  },
  {
    icon: "wallet",
    title: "Versteckte Kosten",
    description:
      "...die entstehen, wenn fehlerhafte Leads Ihr Werbebudget unbemerkt belasten.",
  },
  {
    icon: "scanSearch",
    title: "Fehlende Transparenz",
    description:
      "...da Sie nicht erkennen können, welche Lead-Quellen wirklich Ergebnisse liefern.",
  },
];

const iconMap: Record<
  string,
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
          Warum Sie sich schlechte Leads nicht leisten sollten
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          Unqualifizierte, veraltete oder fehlerhafte Leads schaden nicht nur Ihrer Conversion Rate - sie verbrennen bares Geld. Die häufigsten Probleme:
        </p>
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
