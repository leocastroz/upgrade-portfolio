<template>
  <TheHeader 
    v-if="showHeader"
  />

  <br>

  <div v-show="showName">
    Nome: {{ firstName }}
    <br>
    Sobrenome: {{ lastName }}
  </div>

  <br>

  <div v-if="accessLevel === 'admin'">ADMIN</div>
  <div v-else-if="accessLevel === 'user'">USER</div>
  <div v-else>ANONIMO</div>

  <br>

  <div>
    <div 
      v-for="(obj, index) in todos"
      v-bind:key="obj.id"
      class="todos-item"
    >
      {{ index }} - {{ obj.title }}
    </div>
  </div>
  

  <img
  alt="Vue logo" 
  src="./assets/logo.png"
  >
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TheHeader
  },
  data () {
    return{
      showHeader: true,
      firstName: 'Leonardo',
      lastName: 'Silva Castro',
      showName: true,
      accessLevel: 'use',
      todos: [
  {
    "userId": 1,
    "id": 1,
    "title": "amarelo",
    "completed": false
  },
  {
    "userId": 1,
    "id": 2,
    "title": "azul",
    "completed": false
  },
  {
    "userId": 1,
    "id": 3,
    "title": "vermelho",
    "completed": false
  },
  {
    "userId": 1,
    "id": 4,
    "title": "preto",
    "completed": true
  },
  {
    "userId": 1,
    "id": 5,
    "title": "branco",
    "completed": false
  }
]
    }
  }
}
</script>

<style>
.todos-item{
  background: #2c3e50;
  color: #fff;
  padding: 5px;
  margin: 5px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
