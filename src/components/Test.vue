<template>
    <div>
        <div v-text="title"></div>
        <div v-html="myHtml"></div>
        <div v-if="showName">
            <p>{{user.firstName}}</p>
        </div>
        <div v-else="showName">
                <p>no puedo mostrar nombre</p>
        </div>
        <hr>
        <ul >
            <li v-for="task in tasks">
                {{task.title}}
            </li>
           
        </ul>
        <input type="text" v-model="user.firstName">
        <button type="button" v-on:click="Saludar(user.firstName)">click</button>
        <hr>
        <input type="text" v-on:keyup.enter="typingEnter">
        <hr>
        <div>
            {{fullName}}
        </div>
        <div class="test">
            {{msg}}
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return {
                title: 'Hola Vuejs',
                user:{
                    firstName:'joe',
                    lastName:'McMillian'
                }
                ,myHtml:'<h3>Hola vue</h3>'
                ,showName:false
                ,tasks:[
                    {title:'eat'}
                    ,{title:'dinner'}
                    ,{title:'play'}
                ]
            }
        },
        methods:{
            Saludar(name){
                alert("Hello "+name);
            },
            typingEnter(e){
                console.log("dio un enter");
                //console.log(e.target.value);
               // if(e.target.keyCode==13)
            }
        },
        computed:{
            fullName(){
                return this.user.firstName+' '+this.user.lastName;
            }
        },
        props:{
            msg:{
                type:String,
                default:'Mensaje por defecto'
            }
        }
    }
</script>
<style media="screem">
.test{
    background-color: #eee;
}
</style>