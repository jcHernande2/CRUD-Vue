<template lang="html">
    <div class="users">
        <h1>User component</h1>
        <ul>
            <li v-for="user in users">
                {{user.name}}.' '.{{user.email}}
                <button v-on:click="deleteUser(user)">X</button>
            </li>
        </ul>
        <form v-on:submit.prevent="addUser">
            <input type="text" v-model="newUser.name" placeholder="nombre" value="" >
            <input type="email" v-model="newUser.email" placeholder="email" value="" >
            <button type="submit" >add</button>
        </form>
    </div>
</template>
<script>
  export default{
        data(){
            return {
                users:[
                    {
                        name:'jhon',
                        email:'hernandez@gmail.com',
                        contacted:false
                    },
                     {
                        name:'carlos',
                        email:'car@gmail.com',
                        contacted:false
                    }
                    ,
                     {
                        name:'sergio',
                        email:'ser@gmail.com',
                        contacted:true
                    }
                ],
                newUser:{
                    
                }
            }
            
        },
        methods:{
            addUser(e){
               // e.preventDefault();
                //console.log("agregando user");
                this.users.push(this.newUser);
                this.newUser={};
            },
            deleteUser(user){
                this.users.splice(this.users.indexOf(user),1);
                //alert("eleiminando");
            }
        },
        created(){
            this.$http.get('https://jsonplaceholder.typicode.com/users')
            .then(res=>this.users=res.body);
            //console.log("componente create");
        }
  }
</script>
<style lang="css">
 .users{
     background: #333;
     color:#fff;
 }
</style>