<script setup lang="ts">
import { ref, reactive } from "vue";
import { Button } from "./ui/button";
import { Card, CardHeader, CardContent, CardFooter } from "./ui/card";
import { Label } from "./ui/label";
import { Input } from "./ui/input";
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from "./ui/select";
import { Textarea } from "./ui/textarea";
import { Alert, AlertDescription, AlertTitle } from "@/components/ui/alert";

import { AlertCircle, Building2, Phone, Mail, /*Clock*/ } from "lucide-vue-next";

interface ContactFormeProps {
  firstName: string;
  lastName: string;
  email: string;
  subject: string;
  message: string;
}

const contactForm = reactive<ContactFormeProps>({
  firstName: "",
  lastName: "",
  email: "",
  subject: "Web Development",
  message: "",
});

const invalidInputForm = ref<boolean>(false);

const handleSubmit = () => {
  const { firstName, lastName, email, subject, message } = contactForm;
  console.log(contactForm);

  const mailToLink = `mailto:info@coupling.media?subject=${subject}&body=Hello I am ${firstName} ${lastName}, my Email is ${email}. %0D%0A${message}`;

  window.location.href = mailToLink;
};
</script>

<template>
  <section
    id="contact"
    class="container py-24 sm:py-32"
  >
    <section class="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div>
        <div class="mb-4">
          <h2 class="text-lg text-primary mb-2 tracking-wider">Kontakt</h2>

          <h2 class="text-3xl md:text-4xl font-bold">Wir haben die Antwort auf Ihre Fragen</h2>
        </div>
        <p class="mb-8 text-muted-foreground lg:w-5/6">
          Schreiben Sie uns einfach eine E-Mail und wir melden uns bei Ihnen, Rufen Sie uns kostenlos und unverbindlich an der kommen Sie gleich vorbei:
        </p>

        <div class="flex flex-col gap-4">
          <div>
            <div class="flex gap-2 mb-1">
              <Building2 />
              <div class="font-bold">Adresse</div>
            </div>

            <div>Leopoldstraße 2-8, 32051 Herford</div>
          </div>

          <div>
            <div class="flex gap-2 mb-1">
              <Phone />
              <div class="font-bold">Telefon</div>
            </div>

            <div>+49 (0) 5221 - 34 25 6 - 0</div>
          </div>

          <div>
            <div class="flex gap-2 mb-1">
              <Mail />
              <div class="font-bold">E-Mail</div>
            </div>

            <div>info@coupling.media</div>
          </div>

          <!--<div>
            <div class="flex gap-2">
              <Clock />
              <div class="font-bold">Visit Us</div>
            </div>

            <div>
              <div>Monday - Friday</div>
              <div>8AM - 4PM</div>
            </div>
          </div>-->
        </div>
      </div>

      <!-- form -->
      <Card class="bg-muted/60 dark:bg-card">
        <CardHeader class="text-primary text-2xl"> </CardHeader>
        <CardContent>
          <form
            @submit.prevent="handleSubmit"
            class="grid gap-4"
          >
            <div class="flex flex-col md:flex-row gap-8">
              <div class="flex flex-col w-full gap-1.5">
                <Label for="first-name">Vorname</Label>
                <Input
                  id="first-name"
                  type="text"
                  placeholder="Vorname"
                  v-model="contactForm.firstName"
                />
              </div>

              <div class="flex flex-col w-full gap-1.5">
                <Label for="last-name">Nachname</Label>
                <Input
                  id="last-name"
                  type="text"
                  placeholder="Nachname"
                  v-model="contactForm.lastName"
                />
              </div>
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="email">E-Mail</Label>
              <Input
                id="email"
                type="email"
                placeholder="beispiel@gmail.com"
                v-model="contactForm.email"
              />
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="subject">Betreff</Label>
              

              <Select v-model="contactForm.subject">
                <SelectTrigger>
                  <SelectValue placeholder="Wählen Sie einen Betreff" />
                </SelectTrigger>
                <SelectContent>
                  <SelectGroup>
                    <SelectItem value="Website Check">
                      Website Check
                    </SelectItem>
                    <SelectItem value="Etwas anderes">
                      Etwas anderes
                    </SelectItem>
                  </SelectGroup>
                </SelectContent>
              </Select>
            </div>

            <div class="flex flex-col gap-1.5">
              <Label for="message">Nachricht</Label>
              <Textarea
                id="message"
                placeholder="Ihre Nachricht..."
                rows="5"
                v-model="contactForm.message"
              />
            </div>

            <Alert
              v-if="invalidInputForm"
              variant="destructive"
            >
              <AlertCircle class="w-4 h-4" />
              <AlertTitle>Error</AlertTitle>
              <AlertDescription>
                Es ist ein Fehler aufgekommen. Bitte überprüfen Sie Ihre Angaben.
              </AlertDescription>
            </Alert>

            <Button class="mt-4">Nachricht senden</Button>
          </form>
        </CardContent>

        <CardFooter></CardFooter>
      </Card>
    </section>
  </section>
</template>
