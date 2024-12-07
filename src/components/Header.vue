<template>
  <header :class="{ hidden: isHidden }">

    <img src="../assets/LOGO.png" alt="LOGO">
  </header>
</template>

<script>
export default {
  data() {
    return {
      isHidden: false,
      lastScrollY: 0,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const currentScroll = window.scrollY;
      this.isHidden = currentScroll > this.lastScrollY;
      this.lastScrollY = currentScroll;
    },
  },
};
</script>

<style scoped>
header {
  position: fixed;
  top: 0;
  text-align: center;
  left: 0;
  width: 100%;
  padding: 1rem;
  background-color: rgba(154, 196, 182, 0.8); /* Fondo semi-transparente */
  color: white;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  z-index: 1000; /* Asegura que esté sobre todo */
  transition: transform 0.3s ease, background-color 0.3s ease;
}

header.hidden {
  transform: translateY(-100%);
}

header img {
  margin: 0;

}
</style>
