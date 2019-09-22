<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>
        <input class="item" v-model="inputValue"/>
        <button v-on:click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item 
      v-for="(item, index) of list"
      v-bind:content="item"
      :key="index"
      :index="index"
      @delete="handleDelete"
      ></todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
  components:{
    'todo-item':TodoItem
  },
  data:function(){
    return{
      inputValue:'',
      list:[]
    }
  },
  methods:{
    handleSubmit:function(){
      this.list.push(this.inputValue)
      this.inputValue=''
    },
    handleDelete:function(index){
      this.list.splice(index,1)
    }
  }
 
}
</script>
<style>

</style>