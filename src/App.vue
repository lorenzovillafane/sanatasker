<template>
  <div id="app">
    <Header />
    <main>
      <Content />
    
    </main>
  </div>
</template>

<script>
import Content from './components/Content.vue';
import Header from './components/Header.vue';


export default {
  components: {
    Header,
    Content,
   
  },
};
</script>

<style>
/* Añade estilos específicos del App si es necesario */
</style>
