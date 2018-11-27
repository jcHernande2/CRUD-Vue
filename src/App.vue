<template>
  <div id="app">
    
    <h1>Hola mundo</h1>
    <!--<Test msg="Hola desde componente padre"/>
    <User/>
    -->
    <nav>
      <ul>
        <li>
          <router-link to="/test">
          test
          </router-link>
        </li>
        <li>
         <router-link to="/">
          User
          </router-link>
        </li>
      </ul>
    </nav>
    <hr>
    <router-view></router-view>
  </div>
</template>

<script>

 
 
import Test from './components/Test.vue';
import User from './components/User.vue';

import VueResource from 'vue-resource'
export default {
  
  name: 'App',
  components: {
    Test,
    User,
    VueResource 
  
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
