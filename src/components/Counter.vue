<template>
<div>
    <button type="button" @click="moins"> - </button>
      <span> {{ element }} </span>
    <button type="button" @click="plus"> + </button>
</div>

</template>

<script>

export default {
  name: 'App',  
  data() {
    return {element : 0}
  }, 
  
  methods:{
    moins: function (){
      this.element -= 1
    },
    plus: function(){
      this.element += 1
    }
  }
}
</script>

<style>

</style>
