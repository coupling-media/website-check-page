<script setup lang="ts">
const emit = defineEmits(["close"]);
</script>

<template>
  <div
    class="fixed inset-0 bg-black/50 backdrop-blur-sm flex items-center justify-center z-50"
    @click.self="emit('close')"
  >
    <div
      class="bg-card text-card-foreground w-11/12 max-w-2xl p-6 rounded-xl shadow-lg relative max-h-[90vh] overflow-y-auto"
    >
      <!-- Close -->
      <button
        @click="emit('close')"
        class="absolute top-3 right-6 text-muted-foreground hover:text-foreground text-xl"
        aria-label="Schließen"
      >
        x
      </button>

        <h2 class="text-2xl font-bold mb-6">Impressum</h2>

        <div class="space-y-6 text-sm leading-relaxed text-left">

        <section>
            <p>
            coupling media GmbH<br />
            Leopoldstr. 2–6<br />
            32051 Herford
            </p>
        </section>

        <section>
            <p>
            Handelsregister: HRB 5760<br />
            Registergericht: Bad Oeynhausen
            </p>
        </section>

        <section>
            <h3 class="font-semibold mb-1">Vertreten durch</h3>
            <p>
            Stefanie Jany
            </p>
        </section>

        <section>
            <h3 class="font-semibold mb-1">Kontakt</h3>
            <p>
            Telefon: 05221 / 342560<br />
            E-Mail:
            <a
                href="mailto:info@coupling.media"
                class="underline hover:text-foreground"
            >
                info@coupling.media
            </a>
            </p>
        </section>

        <section>
            <h3 class="font-semibold mb-1">Umsatzsteuer-ID</h3>
            <p>
            Umsatzsteuer-Identifikationsnummer gemäß § 27 a Umsatzsteuergesetz:<br />
            DE 2288 20487
            </p>
        </section>

        <section>
            <h3 class="font-semibold mb-1">Redaktionell verantwortlich</h3>
            <p>
            Stefanie Jany
            </p>
        </section>

        <section>
            <h3 class="font-semibold mb-1">
            Verbraucherstreitbeilegung / Universalschlichtungsstelle
            </h3>
            <p class="text-muted-foreground">
            Wir sind nicht bereit oder verpflichtet, an Streitbeilegungsverfahren vor
            einer Verbraucherschlichtungsstelle teilzunehmen.
            </p>
        </section>

        </div>

    </div>
  </div>
</template>
