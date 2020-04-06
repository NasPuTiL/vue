<template>
    <div>
        <div>
            <p>Wartość: {{newItem}}</p>
            <input type ="text" placeholder="todo" v-model="newItem">
            <button v-on:click="addItem">Add</button>  
        </div>
            <ToDoItem 
                v-for="item in items" 
                v-bind:key="item.id" 
                v-bind:item="item"
                @changeStgatus2="changeStatus"
            />
    </div>
</template>

<script>
import ToDoItem from './ToDoItem.vue';

export default {
    name: 'ToDoAppVue',
    components:{
        ToDoItem
  },
  data(){
    return {
      newItem : "",
      items: [
        {id: 0, title: 'Zrobic zakupy', completed: false},
        {id: 1, title: 'nagrac kurs', completed: true}
      ],
    }
  },
  methods: {
    increase(){
        this.counter++;
    },
    addItem(){
      this.items.push({id: this.items.length, title: this.newItem,completed: false});
      this.newItem = '';
    },
    changeStatus(item){
        item.completed = !item.completed;
    }
  }

}
</script>
