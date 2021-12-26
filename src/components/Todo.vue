<template>
  <div id="todo">
    <p>{{ title }} at {{ time }}</p>
    <Button title="delete" @handleClick="handleClick"/>
  </div>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Todo",
  props: {
    title: String,
    id: String,
    time: String,
  },
  components: {
    Button,
  },
 methods:{
     handleClick(){
         this.$emit('delete-todo', this.id)
        //  console.log(this.id)     
     }
 }
};
</script>

<style>
#todo {
  padding: 3px 0;
  display: flex;
  justify-content: space-between;
}
</style>
