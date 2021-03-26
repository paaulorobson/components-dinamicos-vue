<template>
  <div>

  <h2>Sobre</h2>

  <p v-if="autor">Autor: {{autor}} </p>
  <input type="text" v-model="autor" />
  
  </div>
</template>

<script>
export default {
  data() {
    return {
      autor: ''

    }
  },
  created() {
    console.log('criado!');
  },
  destroyed() {
    console.log('destruído!');
  },
  activated() {
    console.log('Ativado!');
  },
  deactivated() {
    console.log('Desativado');
  },
}
</script>