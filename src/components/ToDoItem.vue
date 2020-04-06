<template>
    <div class ="item" v-bind:class="{completed: item.completed}">
        <h2>{{item.title}}</h2>
        <button @click="change(item)">Done</button>
    </div>
</template>

<script>
export default {
    props: ['item'],
    methods:{
        change(item){
            this.$emit('changeStgatus2', item);
        }
    }
}
</script>


<style scoped>
.item {
  border: 1px solid #cdcdcd;
  margin: 8px;
  padding: 10px;
}
.completed {
  opacity: 0.5;
}
.completed h2{
  text-decoration: line-through;
}

</style>