<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <SideBar></SideBar>
    <CrudTable></CrudTable>
    <v-main style="height: 250px"></v-main>
</template>

<script setup>
    import CrudTable from '@/components/CrudTable.vue'
    import SideBar from '@/components/SideBar.vue'   
</script>