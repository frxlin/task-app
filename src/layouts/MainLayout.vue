<template>
  <q-layout view="hhh LpR fff">

    <q-header reveal bordered class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://plus.unsplash.com/premium_photo-1681487870238-4a2dfddc6bcb?fm=jpg&q=60&w=3000&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8bGlzdGElMjBkZSUyMHRhcmVmYXMlMjBhJTIwZmF6ZXJ8ZW58MHx8MHx8fDA%3D">
          </q-avatar>
          Lista de Tarefa
        </q-toolbar-title>
      </q-toolbar>

      <q-tabs align="left">
        <q-route-tab to="/" label="Home" />
        <q-route-tab to="/lista-tarefas" label="Listas de Tarefas" />
      </q-tabs>
    </q-header>
    
    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script setup>
// import { ref } from 'vue'

</script>