<template>
  <div>
    <h1>Hola mundo en Vue.js</h1>
    <hr/>
    <h1> {{message}} </h1>
    <button v-on:click="cambiar_mensaje"> Cambiar Mensaje</button>
    <hr/>
    <h1>Este boton se ha presionado {{count}} veces</h1>
    <button v-on:click="contador"> contar</button>
    <button v-on:click="reiniciar"> reiniciar</button>
    <hr/>
    <input type="text" placeholder="escriba aquí" v-model="value">
    <h1>{{value}}</h1>
    <hr/>
     <h1 v-if="linterna">Encendido</h1>
     <h1 v-else>Apagado</h1>
    <button v-on:click="cambiar_linterna">Encender/Apagar</button>
    <hr/>
    <h1>Imprimiendo una lista</h1>
    <ul>
      <li v-for="(value, id) in users" v-bind:key="id"> 
        {{id}} -> Nombre: {{value}} 
        </li> 
    </ul>








  </div>
</template>



<script>
export default {
  name: 'App',
  components: {},
  data: function(){
    return {
      message: "Este es un nuevo mensaje!",
      count: 0,
      value: "...",
      users: ["Juan", "Andrea", "Maria", "Pedro"],
      linterna: false
    }
  },
  methods:{
    cambiar_mensaje(){
      this.message = "¡Este es otro mensaje!"
    },
    contador(){
      this.count++
    },
    reiniciar(){
      this.count = 0
    },
    cambiar_linterna(){
      this.linterna = !this.linterna
    }
  }
}
</script>