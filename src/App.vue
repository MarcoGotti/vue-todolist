<script>
export default {
  name: "App",
  data(){
    return {
      list: [
        { 
          todo:'spesa',
          done: false,
        },
        { 
          todo:'meccanico',
          done: false
        },
        { 
          todo:'giornale',
          done: true,
        },
        { 
          todo:'posta',
          done: true,
        },
        { 
          todo:'giardino',
          done: true,
        }
      ]
    }
  }
}
</script>

<template>
  <ul>
   <li v-for="item in list">
<!-- Milestone 2 -->  
      <span @click="item.done=!item.done">X</span>    
      <span class="ml_1" v-if="item.done">{{ item.todo }}</span>
      <span  class="ml_1" v-else></span>    
      
      <!-- aggiungi elemento a lista con input -->
<!-- Milestone 1 -->
    <!-- <li v-if="!item.done">
      <span @click="">X</span>
      {{ item.todo }}
    </li>
    <li class="line_through" v-else>
      {{ item.todo }}
    </li> -->
   </li>
    
  </ul>

</template>

<style>

</style>
