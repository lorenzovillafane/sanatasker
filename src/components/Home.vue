<template>
    <div>
      <component :is="currentComponent"></component>
    </div>
  </template>
  
  <script>
  import Content from '../components/Content.vue';
  import Mobile from '../components/Mobile.vue';
  
  export default {
    data() {
      return {
        currentComponent: null,
      };
    },
    mounted() {
      this.setComponentBasedOnWindowSize();
  
    
      window.addEventListener('resize', this.setComponentBasedOnWindowSize);
    },
    beforeDestroy() {
  
      window.removeEventListener('resize', this.setComponentBasedOnWindowSize);
    },
    methods: {
      setComponentBasedOnWindowSize() {
       
        this.currentComponent = window.innerWidth >= 780 ? Content : Mobile;
      },
    },
  };
  </script>
  
  <style scoped>
 
  </style>
  