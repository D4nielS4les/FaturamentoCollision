<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer">
      <menu-lateral/>
    </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title>Faturamento Collision Centers</v-app-bar-title>
    </v-app-bar>

    <v-main>
      <RouterView/>
    </v-main>
  </v-app>
</template>

<script setup>
  import { ref } from 'vue'
  import MenuLateral from './components/MenuLateral.vue';

  const drawer = ref(null)
</script>

<script>
  export default {
    data: () => ({ drawer: null }),
    itens: [
      {
        title:"Inserir", 
        icon:"mdi-car-arrow-right" ,
        to: "/"
      },
      {
        title:"Tabela", 
        icon:"mdi-grid" ,
        to: "/tabela"
      },

    ]
  }
</script>