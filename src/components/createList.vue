<template>
  <div class="q-pa-md" style="max-width: 400px">
    <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
      <q-input
        filled
        v-model="name"
        label="Título"
        lazy-rules
        :rules="[(val) => (val && val.length > 0) || 'Digite um título']"
      />

      <q-input
        filled
        v-model="descricao"
        label="Descrição"
        lazy-rules
        :rules="[(val) => (val && val.length > 0) || 'Digite uma descrição']"
      />

      <label>Status:</label>
      <br />
      <q-radio v-model="shape" val="line" label="A Fazer" />
      <q-radio v-model="shape" val="rectangle" label="Em Progresso" />
      <q-radio v-model="shape" val="ellipse" label="Concluído" />

      <q-input
        filled
        type="date"
        v-model="data"
        label="Prazo de Conclusão"
        lazy-rules
        :rules="[(val) => (val && val.length > 0) || 'Escolha uma data']"
      />

      <q-btn
        type="submit"
        icon="save"
        label="Salvar"
        stack
        glossy
        color="secondary"
        style="margin-left: 120px"
      />
    </q-form>
  </div>
</template>

<script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  setup() {
    const $q = useQuasar()

    // Definir variáveis corretamente
    const name = ref('')
    const descricao = ref('')
    const shape = ref('line')
    const data = ref('')

    return {
      name,
      descricao,
      shape,
      data,

      onSubmit() {
        $q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Tarefa salva com sucesso!',
        })
      },

      onReset() {
        name.value = ''
        descricao.value = ''
        shape.value = 'line'
        data.value = ''
      },
    }
  },
}
</script>
