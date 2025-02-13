<template>
  <div class="q-pa-lg row items-start q-gutter-xl justify-center">
    <q-card class="my-card">
      <q-card-section class="bg-primary text-white">
        <div class="text-h6">Em 2022 faturamos</div>
        <div class="text-subtitle2">R$ 1.000.000</div>
      </q-card-section>
    </q-card>

    <q-card class="my-card">
      <q-card-section class="bg-primary text-white">
        <div class="text-h6">
          Planos aprovados
          <q-icon name="fa-solid fa-check" />
        </div>
        <div class="text-subtitle2">0</div>
      </q-card-section>
    </q-card>

    <q-card class="my-card">
      <q-card-section class="bg-primary text-white">
        <div class="text-h6">
          Plano com Consultor
          <q-icon name="fa-solid fa-user" />
        </div>
        <div class="text-subtitle2">2</div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {
  setup() {
    return {
      lorem:
        'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    }
  },
}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 250px
</style>
