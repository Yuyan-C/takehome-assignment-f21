<template>
  <div>
    <!-- PART 1: Pass in a "complete" prop here -->
    <Instructions 
    :complete=true />
    <!-- PART 4: Modify the Show component to accept all of these props -->
    <Show
      v-for="show in shows"
      :key="show.id"
      :id="show.id"
      :name="show.name"
      :episodes_seen="show.episodes_seen"
    />

    <br>

    <input v-model="showname" type="text" placeholder="Enter a show ...">
    <button type="button"  @click="add_show">Add a Show</button>
    
  </div>
</template>

<script>
import Instructions from "./Instructions.vue";
import Show from "./Show.vue";
export default {
  components: {
    Instructions,
    Show
  },
  data() {
    return {
      shows: [
        { id: 1, name: "Game of Thrones", episodes_seen: 0 },
        { id: 2, name: "Naruto", episodes_seen: 220 },
        { id: 3, name: "Black Mirror", episodes_seen: 3 }
      ]
    };
  },

  computed: {
  	isDisabled: function(){
    	return this.showname.length == 0;
    }
  },
  
  methods: {

    add_show: function(){
      this.shows.push({
        id: this.shows.length + 1,
        name: this.showname,
        episodes_seen: 0
      }),
      this.showname = "";
    },
  }
};
</script>

<style>
</style>

