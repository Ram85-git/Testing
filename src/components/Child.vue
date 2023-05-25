<template>
    <div class="child">
       <h2>  {{ name }}</h2>
       <h2>{{ user.name }}</h2>
       <button v-on:click="getData()">Call function</button>
    </div>
</template>


<script>

 export default {
    name: 'Child',
    props:{
        name:String,
        user:Object,
        getData:Function
    }

 }



</script>
<style scoped>
  .child{
   
    background-color: aqua;
    height: 150px;
    width: 200px;
   margin: auto;
   border: 5px solid orangered;
   border-radius: 20%;
  }


</style>