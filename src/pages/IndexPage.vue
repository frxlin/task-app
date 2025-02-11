<template>
  <q-page>
    <div class="row col-12">
      Contador: {{ contador }}
    </div>

    <div class="row col-12">
      <q-btn
        label="Teste"
        color="blue"
        @click="handleClick"
      />
    </div>

  
  </q-page>
</template>

<script setup>
import { ref } from 'vue';

//
const contador = ref(0);

const handleClick = () => {
  contador.value += 1;
}
</script>
