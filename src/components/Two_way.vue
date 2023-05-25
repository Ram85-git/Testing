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

    <div class="binding">
         <h1>CSS Binding</h1>
         <h2 :class="{green:colorfull}">CSS binding is going to perform</h2>
         <button v-on:click="colorfull=!colorfull">Apply Style</button>
    </div>
    <br><br>
  <div class="ref">
    <h1> Ref in vue js </h1>
    <input type="text" ref="input"/>
    <button v-on:click="getData2">Click Me</button>
  </div>

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
                ],

                colorfull:false
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
            },
            getData2(){
                this.$refs.input.focus();
                let val=this.$refs.input.value;
                console.log(val);
                this.$refs.input.style.color="red"
            
            }
            
        }



      }


</script>

<style scoped>
    
    h1 {
        color: olivedrab;
    }

    .green{
        background-color: green;
        height: 80px;
        width: 300px;
        margin: auto;
        padding: 10px;
        border-radius: 20px;
        
    }
    .binding{
        background-color: rgb(40, 221, 221);
        height: 200px;
        width: 400px;
        margin: auto;
        padding-top: 20px;
        border-radius: 20px;
        border: 5px solid rgb(10, 68, 175);
    }
    .ref{
        background-color: pink;
        height: 200px;
        width: 250px;
        margin: auto;
        padding-top: 20px;
        padding-left: 10px;
        padding-right: 10px;
        border-radius: 10px;
        border: 5px solid rgb(16, 221, 16);
    }

</style>