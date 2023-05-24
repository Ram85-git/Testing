   <template>
    <h1>Name 1  : {{ getName("Ram dutt bhatt")}}</h1>
    <h1>Name 2  : {{ getName("Govind")}}</h1>

    <h1>All Data : {{ getData()}}</h1>
    <!-- <h1>All Data : {{ getData().name}}</h1> if we want to print only single data -->
   </template>


<script>
export default {
    name :"Methods",
    
    methods: {
        getName(name)
        {
            return name;
        },

        getData()
        {
            return {
                name:'Anil',
                email:'anil@12123.com'
            }
        }
    }
}
</script>