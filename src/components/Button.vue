<template>
  <button id="button" @click="handleClick">{{title}}</button>
</template>

<script>
export default {
    name:"Button",
    props:{
        title:String
    },
    methods:{
        handleClick(){
            this.$emit("handleClick")
        }
    },
    emits:['handleClick']
}
</script>

<style scoped>
    #button{
        outline: none;
        padding: 5px 8px;
        background-color: rgb(80, 80, 80);
        border: none;
        color:rgb(209, 209, 209);
        border-radius: 4px;
        cursor: pointer;
    }
</style>