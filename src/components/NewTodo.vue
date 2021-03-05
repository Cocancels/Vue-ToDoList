<script>
export default {
  name: 'Todo',
  data () {
    return {
        task: []
    }
  },

  methods: {
      newTask() {
        this.$emit('sendTask', this.taskName) 
      }
  }
}
</script>

<template>
  <div id="new">
    <label for="add">Ajouter</label>
    <input v-model="taskName" name="add">
    <button v-on:click="newTask()">Ajouter</button>
  </div>
</template>


<style>
</style>