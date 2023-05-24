<template>
    <h1>Email {{ email }}</h1>
    <h1>Mobile {{ mobile }}</h1>
    <h1>Name {{ name }}</h1>
</template>

<script>

  export default {
    name :"Home",
    data()
    {
        return {
            email:"bhatth@123.com",
            mobile:123456789,
            name:"Ram"

            
        }
    }
  }



</script>

<style scoped >

h1{
    color: green;
}
</style>