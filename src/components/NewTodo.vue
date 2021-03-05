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
    <input placeholder="Nouvelle tâche ..." v-model="taskName" name="add">
    <i v-on:click="newTask()" class="fa fa-plus-circle" aria-hidden="true"></i>

  </div>
</template>


<style>
  #new{
    margin: auto;
    width: 500px;
    display: flex;
    justify-content: space-around;
  }

  #new>input{
    height: 60px;
    font-size: 25px;
    border: none;
    border-bottom: solid 3px rgb(44, 175, 44);
    padding: 0px 30px;
    align-self: center;
  }

  #new>input::placeholder{
    text-align: center;
  }

  #new>input{
    outline:none;
  }

  .fa-plus-circle{
    font-size: 50px;
    color: green;
  }
  
  .fa-plus-circle:hover{
  cursor: pointer;
}

</style>