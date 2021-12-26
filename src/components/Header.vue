<template>
  <div class="wrapper-container">
    <div class="elements-container">
      <div>
        {{ title }}
      </div>
      <Button  title="show add task" @handleClick="() => this.$emit('toggle-add-task')"/>  
    </div>
  </div>
</template>

<script>
import Button from "./Button.vue"
export default {
  name: "Header",
  props: {
    title: String,
  },
  components:{
      Button
  },
  emits:['toggle-add-task']
};
</script>

<style scoped>
.wrapper-container {
  background-color: rgb(230, 230, 230);
  border-radius: 3px;
}

.elements-container {
  padding: 10px 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
