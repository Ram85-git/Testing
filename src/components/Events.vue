<template>
    <h1>Events Component</h1>
    <button v-on:click="test()" > Click Me</button>
    <br><br>
    <button v-on:click="getData('Button 1 clicked')"> Click Me</button>
    <button v-on:dblclick="getData('Button double clicked')"> DoubleClick Me</button>
    <br><br>
    <h1 v-on:mousemove="getConsole()">Events...</h1>
     
    <h2>{{ count }}</h2>
    <button v-on:click="get()">Count it</button>
     <br>
     
</template>

<script>

export default {
    name: "Events",

    data(){

        return {
            count:0
        }
    },


    methods: {
        get(){
             this.count=this.count+1;
        },

        test(){
            alert("function called");
        },


        getData(data)
        {
            alert(data);

        },

        getConsole(){
            console.log("function called")
        }

        

    }
}

</script>

<style scoped>
h1 {
    color: green;
}


</style>