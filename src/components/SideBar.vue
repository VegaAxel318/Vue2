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
        <v-list-item prepend-icon="mdi-table" title="Tabla" value="Table" to="/tabla"></v-list-item>
        <v-list-item prepend-icon="mdi-table" title="Crud Table" value="CrudT" to="/CrudT"></v-list-item>
    </v-list>
    </v-navigation-drawer>
</template>
