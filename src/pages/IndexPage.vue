<template>
  <div class="q-pa-md" style="max-width: 400px">
    <div class="position-absolute top-100 start-100 translate-middle">
    <q-btn dense flat round icon="add" @click="toggleRightDrawer" 
    style="margin-left: 60em;
    margin-top: 50em;
    
    "/>
    </div>
    <q-drawer v-model="rightDrawerOpen" side="right" overlay behavior="desktop" elevated>
      <!-- drawer content -->
      <q-form
        @submit="onSubmit"
        @reset="onReset"
        class="q-gutter-md"
        >
          <q-input
            filled
            v-model="name"
            label="Título"
            lazy-rules
            :rules="[ val => val && val.length > 0 || 'Please type something']"
          />
    
          <q-input
            filled
            v-model="name"
            label="Descrição"
            lazy-rules
            :rules="[ val => val && val.length > 0 || 'Please type something']"
          />
          <q-radio v-model="shape" val="line" label="A Fazer" />
          <q-radio v-model="shape" val="rectangle" label="Em Progresso" />
          <q-radio v-model="shape" val="ellipse" label="Concluido" />
          
    
          <q-input
            filled
            type="date"
            v-model="data"
            label="Prazo de Conclusão"
            lazy-rules
            :rules="[ val => val && val.length > 0 || 'Please type something']"
          />
          
        </q-form>
    </q-drawer>

  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useQuasar } from 'quasar'

const $q = useQuasar()

const name = ref(null)
const age = ref(null)
const accept = ref(false)
const shape = ref('line')
const rightDrawerOpen = ref(false)

const toggleRightDrawer = () => {
  rightDrawerOpen.value = !rightDrawerOpen.value
}

const onSubmit = () => {
  if (accept.value !== true) {
    $q.notify({
      color: 'red-5',
      textColor: 'white',
      icon: 'warning',
      message: 'You need to accept the license and terms first'
    })
  } else {
    $q.notify({
      color: 'green-4',
      textColor: 'white',
      icon: 'cloud_done',
      message: 'Submitted'
    })
  }
}

const onReset = () => {
  name.value = null
  age.value = null
  accept.value = false
}
</script>
