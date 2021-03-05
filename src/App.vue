<script>
import TodoCard from './components/TodoCard.vue'


export default {
  name: 'app',
  components: {
      TodoCard,
  },

    data () {
    return {
      msg: 'Hello, et bienvenue sur la demo TodoList en Vue.js!'
    }
  }
}
</script>

<template>
  <div id="app">
     <section class="hero is-warning is-bold is-fullheight">
      <div class="hero-foot">
        <div class="container">
          <todo-card></todo-card>
        </div>
      </div>
    </section>
  </div>
</template>


<style>
</style>