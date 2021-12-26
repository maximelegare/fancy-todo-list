<template>
  <form @submit.prevent="addTodo" id="input-section-wrapper-container">
    <div class="input-wrapper">
      <p>Title</p>  
      <input type="text" v-model="title" />
    </div>
    <div class="input-wrapper">
      <p>Time</p>  
      <input type="text" v-model="time" />
    </div>
    <Button id="button" title="Add Todo"/>
  </form>
</template>

<script>
import Button from './Button.vue'
export default {
  components:{
      Button
  },
  name: "InputSection",
  data() {
    return {
      title: "",
      time:"",
    };
  },
  methods:{
      addTodo(){
          this.$emit('add-todo', {
              title:this.title,
              time:this.time,
          })
          this.title = ""
          this.time = ""  
      }
  }
};
</script>

<style scoped>
#input-section-wrapper-container {
    /* margin-top: 10px; */
    width: 100%;
    background-color: rgb(230, 230, 230);
    margin: 10px 0;
    padding:10px 0 ;
}
#button{
margin-top: 20px;
}
input{

}
</style>
