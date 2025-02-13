<template>
  <q-page>
    <div class="text-h6">Página da Lista de Tarefas</div>

    <user-cards />

    <a-grafic/>

    <div class="row col-12 q-pa-md justify-center">
      <ATableListaTarefas />
    </div>

    <div class="q-pa-md">
      <q-btn dense flat round icon="add" @click="toggleRightDrawer" style="margin-left: 50em" />

      <q-drawer v-model="rightDrawerOpen" side="right" overlay behavior="desktop" elevated>
        <create-list />
      </q-drawer>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import ATableListaTarefas from 'src/components/ATableListaTarefas.vue'
import CreateList from 'src/components/CreateList.vue'
import UserCards from 'src/components/UserCards.vue'
import AGrafic from 'src/components/AGrafic.vue'

const rightDrawerOpen = ref(false)
const toggleRightDrawer = () => {
  rightDrawerOpen.value = !rightDrawerOpen.value
}
</script>
