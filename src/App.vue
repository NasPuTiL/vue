<template>
  <div>
    <h1>ToDo App</h1>
    <ToDoApp />
  </div>
</template>

<script>
import ToDoAppVue from './components/ToDoApp.vue'

export default {
  components:{
    ToDoApp: ToDoAppVue
  }
}
</script>