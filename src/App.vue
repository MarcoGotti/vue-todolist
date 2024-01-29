<script>
export default {
  name: "App",
  data(){
    return {
      newItem: '',
      list: [
        { 
          todo:'spesa',
          done: true,
        },
        { 
          todo:'meccanico',
          done: true
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
  },
  methods: {
    addTodo(item){
      const newTodo = {
        todo: item,
        done: true
      };
      this.list.push(newTodo);
      this.newItem = '';   
    },
    removeTodo(index){
      console.log('remove todo', index);
      this.list.splice(index, 1);
    }
  }
}
</script>

<template>
  <ul v-if="list.length > 0">
   <li v-for="(item, index) in list">
<!-- **************** Fabio: remove item from array ************************** --> 
    <span class="x" v-on:click="removeTodo(index)">X</span>
    <span :class="!item.done ? 'line_through' : ''" @click="item.done=!item.done">
      {{ item.todo }}
    </span>
    

<!-- *************** toggle onto the X, but item remains in the array *********** -->
      <!-- <span @click="item.done=!item.done">X</span>    
      <span class="ml_1" v-if="item.done">{{ item.todo }}</span>
      <span  class="ml_1" v-else></span> -->   
      
      
    </li>
  </ul>
  <p v-else>Nothing left to do</p>
  
  <input type="text" v-model='newItem' @keyup.enter="newItem !== '' ? addTodo(newItem) : ''">
  <button @click="newItem !== '' ? addTodo(newItem) : ''">Aggiungi</button>

</template>

<style>

</style>
