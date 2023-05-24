<template>

<h1>Two way binding</h1>
     <input type="text" v-model="count" />
     <h3>{{ count }}</h3>
<br>

     <h1>Get input fields value</h1>
    <input type="text" placeholder="Enter email" v-model="email" />
    <br><br>
    <input type="password" placeholder="Enter password" v-model="password" />
    <br><br>
    <button v-on:click="getData()">Get Values</button>
<br><br>

    <h1>Get Checkbox & Radio Button value</h1>
    <h3>Technology</h3>
    <label for="java">Java</label>
    <input type="checkbox" value="java"  v-model="technology" id="java" />
     
    <label for="php">Php</label>
    <input type="checkbox" value="php" v-model="technology" id="php" />
     
    <label for="javascript">javascript</label>
    <input type="checkbox" value="javascript" v-model="technology" id="javascript" />
     <br><br>

     <h3>Who I am</h3>
     <label for="student">Student</label>
     <input type="radio" value="student" v-model="who" name="who" id="student" >
      
     <label for="developer">Developer</label>
     <input type="radio" value="developer" v-model="who" name="who" id="developer" >


    <h4>Selected Technology: {{technology}}</h4>
    <h4> I am a :{{ who }}</h4>
  <br><br>
    <h1 v-if="show">If  Condition</h1>
    <h1 v-else>else condition</h1>
    <button v-on:click="show=!show">Toogle</button>

    <br><br>
    <h1>For Loop in vue js</h1>
    <ul>
        <li v-for="item in course" :key="item">
        {{item}}
        </li>
    </ul>
    <br>
    <br>
    <ul>
        <li v-for="item in user" :key="item.email">

            Name is : {{ item.name }} and Email is :{{ item.email }}

        </li>
    </ul>

</template>


<script>


      
      export default {
        
        name: "Two_way" ,

        data(){
            
            return {
                count:0, 
                technology:[],
                who:null,
                show:true,
                course: ['java','python','SQL'],
                user: [
                    {
                      name: "Anil",
                      email:'anil@12.com'

                    },
                    {
                      name: "Anul",
                      email:'anul@12.com'

                    },
                    {
                      name: "Amit",
                      email:'amit@12.com'

                    },
                ]
            } 

        },
        data1(){
            return {
                email:null,
                password:null,
            }
        },

      
        
        methods:{
            getData(){
                console.log("values: ",this.email,this.password)
            }
        }



      }


</script>

<style scoped>
    
    h1 {
        color: olivedrab;
    }

</style>