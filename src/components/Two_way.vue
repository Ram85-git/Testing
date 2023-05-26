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
  <br>
  <br>
  <h1>Simple Form</h1>
  <label>Email : </label>
  <input type="text" placeholder="Enter email"/>
   <br> <br>

   <br><br>

   <h1>Assignment 1 </h1>
   <br><br>
   <lable>First Name</lable>
   <input type="text" placeholder="Enter First Name" v-model="Fname"/>
   <label>Last Name</label>
   <input type="text" placeholder="Enter Last Name"  v-model="Lname" />
   <label>Address</label>
   <input type="text" placeholder="Enter Address"  v-model="Address"/>
   <button v-on:click="submit">Add</button><br> <br><br><br>
    <br>
    <table  border="2px">
        <tr>
             <th>First Name </th>
             <th>Last Name</th>
             <th>Address</th>
             <th>Check</th>
             <th>Delete</th>
        </tr>
        <tr v-for="(item,index) in items" v-bind:key="index">
            <td :class="{red:isRed}" >{{ item.Fname }}</td>
            <td :class="{red:isRed}">{{ item.Lname }}</td>
            <td :class="{red:isRed}">{{ item.Address}}</td>
        
        
            <td>
                <input type="checkbox"  v-on:click="isRed=!isRed" />
            </td>
            <td>
                <i class="fa-solid fa-trash"  v-on:click.prevent="deleteItem(index)"></i>

            </td>
        </tr>
        <br><br>
    </table>
    <br><br>
   <div class="toggle">
      <user name="Reverse the Name" :alert="reverseMessage" />
      <p>{{ message }}</p>
      <User name="Alert" :alert="getUserName" />
</div>
 
 </template>


<script>
      
      import User from './User.vue'

      
      export default {
        name: "Two_way" ,
        components:{
            User
        },




        data(){
            
            return {
                childUser:"",

                count:0, 
                technology:[],
                items:[],
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

                Fname:'',
                Lname:'',
                Address:'',
                isRed:false,
                colorfull:false,
                
                form: {

                    
                },
                message:'Developer',
            } 

        },
        data1(){
            return {
                email:null,
                password:null,

            }
        },
        methods:{

            getUserName(name){
                alert("hello from parent")
                this.childUser = name
                
            },
            reverseMessage: function(){
                this.message=this.message.split("").reverse().join("")

            }
            ,
            getData(){
                console.log("values: ",this.email,this.password)
            },
            getData2(){
                this.$refs.input.focus();
                let val=this.$refs.input.value;
                console.log(val);
                this.$refs.input.style.color="red"
            
            },
            Add(){
                console.log("Data is added" , this.form);
            },

            submit: function(){
                
                this.items.push({'Fname': this.Lname,
                'Lname':this.Lname,
                'Address':this.Address});

                this.Fname="";
                this.Lname="";
                this.Address="";

            },
            deleteItem(index){
                this.items.splice(index,1);
            }
        },



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
    

    table{
        margin: auto;
        
        width: 900px;
    }
    
    .red{
        color: red;
    }

    .my::v-deep .my1 {
        background-color: blue;
    }

    .toggle{
        height: 200px;
        width: 250px;
        background-color: orange;
        margin: auto;
        padding: 15px;
        border: 5px solid green;
        
    }










</style>