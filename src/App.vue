<script>
export default {
  name: "App",
  data(){
    return {
      newItem: '',
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
          done: false,
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
      if (item !== ''){
        const newTodo = {
                          todo: item,
                          done: true
                        };
        this.list.push(newTodo);
        this.newItem = '';
      }
   
    },
    removeTodo(index){
      console.log('remove todo', index);
      this.list.splice(index, 1);
    }
  }
}
</script>

<template>
  <div class="container p-5">
    <div class="card col-3 m-auto ">
      <div class="card-body">
        <h1>To Do</h1>
        <ul class="list-group" v-if="list.length > 0">
          <li class="list-group-item" v-for="(item, index) in list">
<!-- **************** Fabio: remove item from array ************************** --> 
            <span class="x" v-on:click="removeTodo(index)">X</span>
            <span :class="{'line_through' : !item.done}" @click="item.done=!item.done">
              {{ item.todo }}
            </span>
          </li>
        </ul>
<!-- *************** toggle onto the X, but item remains in the array *********** -->
      <!--
      <li>
        <span @click="item.done=!item.done">X</span>    
        <span class="ml_1" v-if="item.done">{{ item.todo }}</span>
        <span  class="ml_1" v-else></span>
      </li> -->  
        <p v-else>Nothing left to do</p>   
      </div>
      <div class="m-3">
        <input type="text" v-model='newItem' @keyup.enter="addTodo(newItem)">
        <button class="m-1" @click="addTodo(newItem)">Aggiungi</button>
      </div>

    </div>
  </div>
 


</template>

<style>

</style>
