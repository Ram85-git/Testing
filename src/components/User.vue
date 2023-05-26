<template>
    
    <div class="my">
       <button class="my1"  v-on:click="alert">{{ name }}</button>
    </div>
    
    

    
</template>



<script>
    export default {
        name:"User",

        props:[
              'alert','name'
        ]
    }




   
</script>