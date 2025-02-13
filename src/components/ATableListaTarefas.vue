<template>
  <q-table
    flat
    bordered
    ref="tableRef"
    class=" col-12"
    tabindex="0"
    title="Lista de Tarefas"
    :rows="rows"
    :columns="columns"
    row-key="name"
    v-model:selected="selected"
    :filter="filter"
    @keydown="onKey"
  >
    <template v-slot:top-right>
      <q-input borderless dense debounce="300" v-model="filter" placeholder="Search">
        <template v-slot:append>
          <q-icon name="search" />
        </template>
      </q-input>
    </template>

    <template v-slot:body-cell-actions="props">
      <q-td :props="props">
        <q-btn color="primary" @click="editRow(props.row)" icon="edit" size="sm" flat />
        <q-btn color="negative" @click="openConfirmDialog(props.row)" icon="delete" size="sm" flat />
      </q-td>
    </template>
  </q-table>

  <!-- Dialog de confirmação -->
  <q-dialog v-model="confirm" persistent>
    <q-card>
      <q-card-section class="row items-center">
        <q-avatar icon="warning" color="negative" text-color="white" />
        <span class="q-ml-sm">Você tem certeza que deseja excluir "{{ selectedRow?.name }}"?</span>
      </q-card-section>

      <q-card-actions align="right">
        <q-btn flat label="Cancelar" color="primary" v-close-popup />
        <q-btn flat label="Confirmar" color="negative" @click="deleteRow(selectedRow)" />
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>

<script setup>
import { ref } from 'vue'

const columns = [
  {
    name: 'desc',
    required: true,
    label: 'Título',
    align: 'center',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: 'Status', align: 'center', label: 'Status', field: 'status' },
  { name: 'Prazo', label: 'Prazo', field: 'prazo' },
  { name: 'actions', label: 'Ações', field: 'actions' }
]

const rows = ref([
  { id: 1, name: 'Estudar', status: 'A Fazer', prazo: '2023-12-31' },
  { id: 2, name: 'Academia', status: 'Feito', prazo: '2023-12-31' }
])

const filter = ref('')
const selected = ref([])

// Variáveis de controle do diálogo
const confirm = ref(false)
const selectedRow = ref(null)

function editRow(row) {
  console.log('Editando:', row)
  // Lógica para editar
}

// Abre o diálogo de confirmação
function openConfirmDialog(row) {
  selectedRow.value = row
  confirm.value = true
}

// Função para excluir a linha após confirmação
function deleteRow(row) {
  console.log('Deletando:', row)
  const index = rows.value.findIndex(item => item.id === row.id)
  if (index !== -1) {
    rows.value.splice(index, 1)  
  }
  confirm.value = false 
}
</script>
