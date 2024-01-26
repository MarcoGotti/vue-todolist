<script>
export default {
  name: "App",
  data(){
    return {
      list: [
        { 
          todo:'spesa',
          done: true
        },
        { 
          todo:'meccanico',
          done: true
        },
        { 
          todo:'giornale',
          done: false
        },
        { 
          todo:'posta',
          done: true
        },
        { 
          todo:'giardino',
          done: true
        }
      ]
    }
  }
}
</script>

<template>
  <div>
   <template v-for="item in list">
    <li v-if="item.done">
      {{ item.todo }}
    </li>
    <li v-else></li>
   </template>
    
  </div>

</template>

<style>

</style>
