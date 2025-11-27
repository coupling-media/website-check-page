<script setup lang="ts">
import { Marquee } from "@selemondev/vue3-marquee";
import "@selemondev/vue3-marquee/dist/style.css";

interface Sponsor {
  logo: string;   // Pfad zur Bilddatei
  alt: string;    // Alternativtext
}


const sponsors: Sponsor[] = [
  { logo: "/sponsors/dufährst.png", alt: "DuFährst" },
  { logo: "/sponsors/smart2i.png", alt: "Smart2i" },
  { logo: "/sponsors/bonsaischule.png", alt: "Bonsaischule Enger" },
  { logo: "/sponsors/schüco.png", alt: "Schüco Bielefeld" },
  { logo: "/sponsors/butch.png", alt: "Butch" },
  { logo: "/sponsors/danielbuksch.png", alt: "Daniel Buksch" },
  { logo: "/sponsors/denkwerkherford.png", alt: "Denkwerk Herford" },
  { logo: "/sponsors/dulehrst.png", alt: "DuLehrst" },
  { logo: "/sponsors/jeansfritz.png", alt: "JeansFritz" },
  { logo: "/sponsors/ksb.png", alt: "Kreissportbund Herford" },
  { logo: "/sponsors/maschinenbau.png", alt: "Nachwuchsstiftung Maschienenbau" },
  { logo: "/sponsors/ohntrup.png", alt: "Ohntrup" },
  { logo: "/sponsors/perfact.png", alt: "Perfact" },
  { logo: "/sponsors/popupbau.png", alt: "Popupbau" },
  { logo: "/sponsors/porzellantreff.png", alt: "Porzellantreff" },
  { logo: "/sponsors/seh.png", alt: "SEH" },
  { logo: "/sponsors/suh.png", alt: "Starke und Höcker" },
];
</script>

<template>
  <section
      id="sponsors"
      class="max-w-[75%] mx-auto pb-24 sm:pb-32"
  >
    <h2 class="text-lg md:text-xl text-center mb-6">Unsere Kunden</h2>

    <div class="mx-auto">
      <Marquee
          class="gap-[3rem]"
          :pauseOnHover="false"
          :fade="true"
          innerClassName="gap-[3rem]"
      >
        <div
            v-for="{ logo, alt } in sponsors"
            :key="alt"
            class="flex items-center justify-center w-[130px] h-[130px] bg-transparent"
        >
          <img
              :src="logo"
              :alt="alt"
              class="max-h-full max-w-full object-contain rounded-xl"
          />
        </div>
      </Marquee>
    </div>
  </section>
</template>

