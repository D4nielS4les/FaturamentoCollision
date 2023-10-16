
<template>
  <v-card>
    <v-layout>
      <v-navigation-drawer
        expand-on-hover
        rail
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/men/35.jpg"
            title="Daniel Sales"
            subtitle="dsr.daniel.sales@gmail.com"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-car-arrow-right" title="Inserir"         value="inserir" to="./"></v-list-item>
          <v-list-item prepend-icon="mdi-grid"            title="Planilha"        value="planilha" to="./tabela"></v-list-item>
          <v-list-item prepend-icon="mdi-finance"         title="Gráficos"        value="graficos"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main style="height: 250px"></v-main>
    </v-layout>
  </v-card>
</template>