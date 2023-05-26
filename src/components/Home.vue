<template>
    <h1>Email {{ email }}</h1>
    <h1>Mobile {{ mobile }}</h1>
    <h1>Name {{ name }}</h1>
    <Child name ="Anil siddhu" :user="user" :getData="getData"/>

</template>

<script>

  import Child from './Child.vue'
  export default {
    name :"Home",

    components: {
      Child

    },

    data()
    {
        return {
            email:"bhatth@123.com",
            mobile:123456789,
            name:"Ram",
            user:{name:'Peter',email:'peter@123.com'}

            
        }
    },

    methods: {
      getData(){
        console.log("parent function called")
        alert("hello")
      }
    }
  }



</script>

<style scoped >

h1{
    color: green;
}
</style>