<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";

import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel";

import { Star } from "lucide-vue-next";

interface ReviewProps {
  image: string;
  name: string;
  userName: string;
  comment: string;
  rating: number;
}

const reviewList: ReviewProps[] = [
  {
    image: "jf-logo.png",
    name: "Falko Schäfer, Leitung E-Commerce",
    userName: "JEANS FRITZ",
    comment:
      "Die Jeans Fritz Handelsgesellschaft für Mode mbH arbeitet bereits seit Jahren mit coupling media zusammen und mit von deren Service und Kompetenz sehr zufrieden. Sympathisches Team mit kompetenter und lösungsorientierter Beratung. Viele gute Anregungen und aktives Anstoßen von Neuerungen und Verbesserungen sowie immer ein offenes Ohr und Hilfestellung.",
    rating: 5.0,
  },
  {
    image: "schueco-logo.png",
    name: "Schüco",
    userName: "Schüco International KG",
    comment:
      "Coupling.media hat uns bei unserer ersten größeren HR-Online-Marketing-Kampagne begleitet. Mit den richtigen Fragen, kompetenten Ansprechpartnerinnen und einem tollen Team! So haben wir gemeinsam über Online- und SocialMedia Marketing genau die richtige Zielgruppe erreicht.",
    rating: 5.0,
  },

  {
    image: "dufaehrst-logo.png",
    name: "Michael Holler, Inhaber",
    userName: "DuFährst Die Fahrschule",
    comment:
      "Nach 3 Jahren ist man endlich angekommen und hat die professionelle Dienstleistung gefunden. Einfach eine super gute Internetseite die es geworden ist. Ich hoffe noch auf viele weitere solcher Projekte und das Team Du Fährst fühlt sich gut aufgehoben bei euch. Nach der dritten Online Marketing Agentur ist diese wirklich die beste.",
    rating: 5.0,
  },
  {
    image: "logo-bucksch-hand.jpg",
    name: "Daniel Bucksch, Inhaber",
    userName: "Malermeister Bucksch",
    comment:
      "Ein sehr freundliches Team, zeitnahe Umsetzung unserer Wünsche, kreative Ideen und Vorschläge, immer gut erreichbar und eine faire Abrechnung. Die Zusammenarbeit mit dem Coupling Media-Team können wir nur wärmstens weiterempfehlen.",
    rating: 5.0,
  },
  {
    image: "ksb-logo.png",
    name: "Nils Wörmann, Geschäftsführer",
    userName: "Kreissportbund Herford e.V",
    comment:
      "Eine schnelle und kreative Umsetzung unserer Vorstellungen führte zu einer benutzerfreundlichen Seite. Der Support ist jederzeit zuverlässig.",
    rating: 5.0,
  },
  {
    image: "bonsai-logo.png",
    name: "Tobias Pieper, Inhaber",
    userName: "Bonsaischule Enger",
    comment:
      "Das Team von coupling media hat uns erfolgreich und souverän bei dem Aufbau eines komplett neuen Online-Shops unterstützt. Das Ergebnis hat am Ende unsere Erwartungen übertroffen und die freundliche, professionelle und kundenorientierte Zusammenarbeit ist der Grund, warum wir auch heute noch gerne Kunden bei coupling media sind!",
    rating: 5.0,
  },
];
</script>

<template>
  <section
    id="testimonials"
    class="container py-24 sm:py-32"
  >
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        Kundenerfahrungen
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Das sagen unsere Kunden über uns
      </h2>
    </div>

    <Carousel
      :opts="{
        align: 'start',
      }"
      class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    >
      <CarouselContent class="items-stretch">
        <CarouselItem
          v-for="review in reviewList"
          :key="review.name"
          class="md:basis-1/2 lg:basis-1/3 h-full flex"
        >
          <Card class="bg-muted/50 dark:bg-card h-[420px] flex flex-col">
            <CardContent class="pt-6 pb-0 flex-1">
              <div class="flex gap-1 pb-6">
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
                <Star class="size-4 fill-primary text-primary" />
              </div>

              "{{ review.comment }}"
            </CardContent>

            <CardHeader>
              <div class="flex flex-row items-center gap-4">
                <Avatar>
                  <AvatarImage
                    :src= "review.image"
                    alt="@radix-vue"
                  />
                  <AvatarFallback>SV</AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{{ review.name }}</CardTitle>
                  <CardDescription>{{ review.userName }}</CardDescription>
                </div>
              </div>
            </CardHeader>
          </Card>
        </CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </Carousel>
  </section>
</template>
