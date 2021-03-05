<script>
export default {
  name: 'List',
  data () {
    return {
    }
  },

  props: ['tasks'],

  methods: {
      changeColor(element){
          element.done = true;
          console.log(element)
      }
  }
}




</script>

<template>
  <div id="list">

    <ul>
        <li class="todo-list" v-for="(task, index) in tasks" :key="(task, index)">
            <input v-on:click="changeColor(task)" type="checkbox" value="isDone">
            <p v-bind:class= "{green: task.done}">{{ task.name }}</p>
            <button>Supprimer</button>
        </li>
    </ul>
  </div>
</template>


<style>

.green{
    color: green
}
</style>