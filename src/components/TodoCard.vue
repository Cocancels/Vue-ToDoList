<script>
import TodoList from '../components/TodoList.vue'
import NewTodo from '../components/NewTodo.vue'



export default {
  name: 'Card',
    components: {
        NewTodo,
        TodoList
    },

  data () {
      return{
         tasks : [],
      }
  }, 

  methods: {
      addTask(task){
          var newTask = {
              name : task,
              done: false
          };

          this.tasks.push(newTask)
          console.log(this.tasks)
      },

      checkTask(index){
          if(index.done == false){
          index.done = true;
        }
        else{
            index.done = false;
          }
      },

      removeTask(index){
          this.tasks.splice(this.tasks.indexOf(index), 1)
      }

    },
  

  computed: { 
      dataDate: function(){
        var date = new Date();
        let days = ["Dimanche", "Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi"]
        let months = ["Janvier", "Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Août", "Septembre", "Octobre", "Novembre", "Décembre"]

        var dayNumber = date.getDate()
        var actualDay = days[date.getDay()]
        var actualMonth = months[date.getMonth()]
       
        return actualDay + " " + dayNumber + " " + actualMonth 
      }
  }
}
</script>

<template>
  <div id="app">
      <div class="card">
        <div class="card-header">
            <p class='date'>{{ dataDate }}</p>
            <p class="title-p">VuesJs Tutorial ToDo List</p>
            <p class='length'>{{ tasks.length }} tâches</p>
        </div>
        <div class="card-content">
            <new-todo @sendTask=addTask ></new-todo>
            <todo-list @remover=removeTask @check=checkTask :tasks="tasks"></todo-list>
        </div>
      </div>
  </div>
</template>



<style>
    .card{
        margin-top: 400px
    }

    .card-header{
        justify-content: space-between;
        padding: 15px;
    }

    .title-p{
        color: rgb(20, 185, 190);
        font-size: 30px;
    }

    .date, .length{
        font-size: 20px;
    }

    

</style>