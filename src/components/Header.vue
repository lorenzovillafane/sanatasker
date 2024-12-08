<template>
  <header :class="{ hidden: isHidden }">
  <div class="containerHeader">
    <div class="socialContainer"> <a href=""><img src="../assets/icons/instagram.png" alt="" class="logonone"></a>
   <a href=""><img src="../assets/icons/linkedin.png" alt=""class="logonone"></a>
   <a href=""><img src="../assets/icons/whatsapp.png" alt=""class="logonone"></a></div>
    <div>
          <img src="../assets/LOGOSANATAKER.png" alt="LOGO">
    </div>

  <div class="socialContainer">
    <a href=""><img src="../assets/icons/instagram.png" alt=""></a>
   <a href=""><img src="../assets/icons/linkedin.png" alt=""></a>
   <a href=""><img src="../assets/icons/whatsapp.png" alt=""></a>
  </div>
   
    </div>
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
  background-color: rgba(85, 173, 155, 0.8); /* Fondo semi-transparente */
  color: white;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  z-index: 1000; /* Asegura que esté sobre todo */
  transition: transform 0.3s ease, background-color 0.3s ease;
}

header.hidden {
  transform: translateY(-100%);
}
.containerHeader{display: flex;
justify-content: space-between;
align-items: center;}
.logonone{display: none;}
.socialContainer{width: 300px;}
header img {
  margin: 0;
width: 150px;
}
a img{width: 50px;
margin: 15px;}
</style>
