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
        }
    }
</script>
<style>
</style>