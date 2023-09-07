<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <v-navigation-drawer
      expand-on-hover
      rail
    >
      <v-list>
        <v-list-item
          title="Opciones"
        ></v-list-item>
      </v-list>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item prepend-icon="mdi-view-dashboard" title="Home" value="Home" to="/"></v-list-item>
        <v-list-item prepend-icon="mdi-table" title="Tabla" value="Image" to="/tabla"></v-list-item>
      </v-list>
    </v-navigation-drawer>
    <Table> </Table>
    <v-main style="height: 250px"></v-main>

</template>

<script setup>
import Table from '@/components/Table.vue'
</script>
