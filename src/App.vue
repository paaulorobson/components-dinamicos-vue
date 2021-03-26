<template>
  <div id="app">
  
    <h1>Components Dinâmicos</h1>

    <div class="wrapper">
      <div>

      <button @click="componentSelecionado= 'Home'">Home</button>
      <button @click="componentSelecionado= 'Sobre'">Sobre</button>
      <button @click="componentSelecionado= 'Contato'">Contato</button>

      </div>
<!-- O atributo include diz quais components quer manter em cache, o exclude diz qual não quer manter -->
      <keep-alive :include="Sobre">
        <component :is="componentSelecionado" />
      </keep-alive>

    </div>

  </div>
</template>

<script>
import Home from './components/Home';
import Sobre from './components/Sobre';
import Contato from './components/Contato';

/*Quando alternamos entre components dinamicos uma nova instância é criada. Para manter a mesma instância usamos o keep-alive */

// Mantém em cache essa instância dos components

/* O ciclo de vida normal do vue perde sentido quando usamos os components dinâmicos com keep-alive*/

/*Components Dinâmicos com keep-alive possuem 2 ciclos de vida (Lifecicle Hooks):

 activated() {
   
 },
 deactivated() {
   
 },
 */


export default {
  name: 'App',
  components: {
    Home,
    Sobre,
    Contato,
  },

  data() {
    return {
      componentSelecionado: 'Home',
    }
   
  }
}
</script>

<style>
body {
    margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color:blueviolet;

}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #fff;
  padding: 0 20px;
}

.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
 
}

button {
  margin: 5px 0;
  display: flex;
  flex-direction: column;
  width: 100px;
  height: 30px;
  display: block;
  border: 1px solid #ddd;
  border-radius: 4px;
  background-color: transparent;
  color: #fff;

}
 
</style>
