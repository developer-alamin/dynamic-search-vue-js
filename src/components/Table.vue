<script setup>
import {countris} from "../assets/app.js";
const props = defineProps(['label','modelValue']);

function Search(){
  return countris.filter(item=>{
     return item.name.toLowerCase().includes(props.modelValue.toLowerCase()) || item.age.toString().includes(props.modelValue) || item.position.toLowerCase().includes(props.modelValue.toLowerCase()) || item.village.toLowerCase().includes(props.modelValue.toLowerCase()) ;
  })
}
</script>
<template>
	<table class="table table-bordered table-striped table-inverse table-hover">
      <thead>
        <tr>
          <th>Name</th>
          <th>Age</th>
          <th>Position</th>
          <th>Village</th>
        </tr>
      </thead>
      <tbody>
        <tr v-if="Search().length > 0" v-for="(country,index) in Search()" :key="index">
           <td>{{ country.name }}</td>
           <td>{{ country.age }}</td>
           <td>{{ country.position }}</td>
           <td>{{ country.village }}</td>
        </tr> 
        <tr v-else>
         <td colspan="4" class="text-center">No Value Of Search</td>
        </tr>
      </tbody>
    </table>
</template>