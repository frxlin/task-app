<template>
   
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
      
  </template>
  
  <script>
  
import { useQuasar } from 'quasar'
  import { ref } from 'vue'
  
  export default {
    setup () {
      const $q = useQuasar()
  
      const name = ref(null)
      const age = ref(null)
      const accept = ref(false)
  
      return {
        name,
        // eslint-disable-next-line no-undef
        descricao,
        accept,
  
        onSubmit () {
          if (accept.value !== true) {
            $q.notify({
              color: 'red-5',
              textColor: 'white',
              icon: 'warning',
              message: 'You need to accept the license and terms first'
            })
          }
          else {
            $q.notify({
              color: 'green-4',
              textColor: 'white',
              icon: 'cloud_done',
              message: 'Submitted'
            })
          }
        },
  
        onReset () {
          name.value = null
          age.value = null
          accept.value = false
        }
      }
    }
  }
  </script>
  