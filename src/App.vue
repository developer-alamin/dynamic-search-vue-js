<script setup>
  import { ref,reactive } from 'vue';
  import Header from "./components/header.vue";
  import Table from "./components/Table.vue";
  const s = ref("");
</script>
<template>
  <div class="container">
    <div class="row">
      <Header/>
    </div>  
    <div class="row">
       <div class="col-3">
          <input v-model="s" type="search" class="form-control" placeholder="Search..">
        </div>
    </div>
    <br>
    <div class="row">
      <div class="col-12">
        <Table label="Alamin" v-model="s"/>
      </div>
    </div>  
  </div>
</template>
<style scoped>
</style>
