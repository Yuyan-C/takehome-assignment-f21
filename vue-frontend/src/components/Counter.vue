<template>
  <!-- <p>I'm a Counter!</p> -->
  <div>
    <p>episodes_seen: {{ episodes_seen }}</p>
    <button @click="increment">+1</button>
    <button @click="decrement">-1</button>
  </div>
 
</template>

<script>
export default {
  data() {
    return {
      count: 0
    };
  },

  props:{
    episodes_seen: Number,
  },

  methods: {
    increment: function(){
      this.episodes_seen +=1;
    }, 
    
    decrement: function(){
      if (this.episodes_seen > 0){
        this.episodes_seen -=1;
      } else{
        alert("episodes seen cannot be negative!")
      }
    }
  }
};
</script>

<style>
</style>