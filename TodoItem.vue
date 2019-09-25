  <!-- eslint-disable no-new  -->
<template>
<li class="item" @click="handleDelete">{{content}}</li>
</template>

<script>
/* eslint-disable */
export default {
  props: ['content','index'],
  methods:{
    handleDelete:function(){
      this.$emit('delete',this.index)
    }
  }
}
</script>

<style>
.item{
  color:red;
}
</style>
