<template>
  <!-- PART 4: Add your code here -->
  <div>
    <p>Show name: {{ name }}</p>
    <Counter 
    :episodes_seen = episodes_seen />
  </div>
</template>

<script>
// PART 4: Add your code here
import Counter from './Counter.vue'
export default {
  props:{
    id: Number,
    name: String,
    episodes_seen: Number,

  },
  
  components:{
    Counter
  }

};
</script>

<style>
</style>