<script>
export default {
  name: "App",
  data(){
    return {
      list: [
        { 
          todo:'spesa',
          done: false,
          line: true
        },
        { 
          todo:'meccanico',
          done: false,
          line: true
        },
        { 
          todo:'giornale',
          done: true,
          line: true
        },
        { 
          todo:'posta',
          done: true,
          line: true
        },
        { 
          todo:'giardino',
          done: true,
          line: true
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
