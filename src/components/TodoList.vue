<script>
export default {
  name: 'List',
  data () {
    return {
    }
  },

  props: ['tasks'],

  methods: {
      check(index){
          this.$emit('check', index) 
      },

      remover(index){
          this.$emit('remover', index) 
      }
   }
}




</script>

<template>
  <div id="list">

    <ul>
        <li class="todo-list" v-for="(task, index) in tasks" :key="(task, index)">
            <input v-on:click="check(task)" type="checkbox" value="isDone" id="checkbox">
            <p v-bind:class= "{checked: task.done}">{{ task.name }}</p>
            <i v-on:click="remover(task)" class="fa fa-trash" aria-hidden="true"></i>
        </li>
    </ul>
  </div>
</template>


<style>

.checked{
    text-decoration: line-through;
}

.todo-list{
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
}

#checkbox{
  transform: scale(2);
}

.todo-list>p{
  font-size: 20px;
}

.todo-list>i{
  font-size: 30px;
  color: red;
}

.todo-list>i:hover{
  cursor: pointer;
}

</style>