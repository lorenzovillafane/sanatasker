<template>
    <div>
      <!-- Sección Hero modificada -->
      <section
        v-for="(section, index) in heroSections"
        :key="index"
        class="hero"
      >
        <div class="hero-inner">
          <figure></figure>
          <div class="hero__title">
            <template v-if="section.type === 'text-image'" id="sectionOne" >
              <img :src="section.image" alt="Imagen hero" class="hero-img" />
              <p id="pSectionOne">{{ section.text }}</p>
            </template>
            <template v-if="section.type === 'text-image2'" id="sectionTwo" >
             <div><h3>Sobre Mi</h3>
                <p id="pSectionTwo">{{ section.text }}</p>
              </div>
               <img :src="section.image" alt="Imagen hero" class="hero-img2" />
              
              
            </template>
            <template v-else-if="section.type === 'gallery'"   >
              <div id="galleryContainer">
                   <h3>Servicios que ofrezco</h3>
              <div class="gallery"> 
                <div v-for="(item, idx) in section.items" :key="idx">
                  <img :src="item.image" :alt="item.title" />
                  <p>{{ item.title }}</p>
                </div>
              </div>
              </div>
          
            </template>
            <template v-else-if="section.type === 'testimonial'">
              <blockquote>{{ section.quote }}</blockquote>
              <img :src="section.image" alt="Imagen hero" class="hero-img" />
              <p id="pSectionFour">{{ section.author }}</p>
            </template>
          </div>
        </div>
      </section>
  
      <!-- Sección de contenido original -->
      <section class="content">
        <article class="content__inner">
          <h1 class="content__title">Contactame!</h1>
          <h3 class="content__author">Tu primer consulta es gratuita</h3>
  
          <div class="footer__form">
      
      <form>
        <input type="text" placeholder="Nombre" />
        <input type="email" placeholder="Tu correo" />
        <textarea placeholder="Introduzca un mensaje"></textarea>
        <button type="submit">Enviar</button>
      </form>
      <div class="footer__socials">
        <a href="#" target="_blank">Linkedin</a>
        <a href="#" target="_blank">whatsapp</a>
        <a href="#" target="_blank">Instagram</a>
      </div>
    </div>
        </article>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    name: "Content",
    data() {
      return {
        heroSections: [
          {
            type: "text-image",
            image: "src/assets/Girl meditating in the lotus position.png",
            text: "Delegar puede ser una forma sencilla de encontrar paz mental",
          },
          {
            type: "text-image2",
            image: "src/assets/JULI-removebg-preview.png",
            text: "Hola, soy Juli creadora de Sanatasker. Este proyecto surge de la idea de ayudarte a aliviar el peso de vivir con una enfermedad crónica o acompañar a alguien en esta situación, de modo que la responsabilidad que esto implica no sea una carga adicional en tu vida, ni en la de quienes te rodean. Mi compromiso es brindarte apoyo desde la organización y la empatía para centrarte en lo que realmente importa y sentirte tranquilo en cada paso del camino.",
          },
          {
            type: "gallery",
            items: [
              { image: "src/assets/Woman working on computer and having phone conversation.png", title: "Gestion y organizacion de turnos" },
              { image: "src/assets/Girl with a Letter.png", title: "Recordatorios" },
              { image: "src/assets/Girl stands near huge calendar.png", title: "Facilitar tramites con obras sociales" },
            ],
          },
          {
            type: "testimonial",
            image: "src/assets/JULI.png",
            quote: "Este es un testimonio de un cliente satisfecho.",
            author: "- Cliente Anónimo",
          },
        ],
      };
    },
  };
  </script>
  
  
  <style lang="scss" scoped>
  @import url("https://fonts.googleapis.com/css?family=Courgette|Roboto");

  
  $ff-serif: "Courgette", serif;
  $ff-sans-serif: "Roboto", sans-serif;
  $color-accent: #a9dfbf;
  
  $assets: (
    1: "1506260408121-e353d10b87c7",
    2: "1506744038136-46273834b3fb",
    3: "1523712999610-f77fbcfc3843",
    4: "1501785888041-af3ef285b470"
  );
  
  @function image($key) {
    $id: map-get($assets, $key);
    @return url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/225363/photo-" + $id + ".jpg");
  }
  
  .footer__form {
    max-width: 600px;
    margin: 0 auto;
    text-align: center;

    h2 {
      font-family: 'Courgette', serif;
      font-size: 2rem;
      margin-bottom: 1rem;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 1rem;

      input,
      textarea {
        width: 100%;
        padding: 0.75rem;
        font-size: 1rem;
        border: 1px solid #ddd;
        border-radius: 5px;
      }

      button {
        padding: 0.75rem 1.5rem;
        background-color: #a9dfbf;
        border: none;
        color: white;
        font-size: 1rem;
        cursor: pointer;
        border-radius: 5px;
        transition: background-color 0.3s ease;

        &:hover {
          background-color: #87c99e;
        }
      }
    }

    .footer__socials {
      margin-top: 2rem;

      a {
        margin: 0 0.5rem;
        font-size: 1.25rem;
        color: #666;
        text-decoration: none;

        &:hover {
          color: #333;
        }
      }
    }
  }




  * {
    box-sizing: border-box;
    
    font-family: $ff-serif;
  }
  
  p {
    font-family: $ff-serif;
    font-size: 2.25rem;
    line-height: 1.5;
  }

  #pSectionOne{   
    margin-top: 50px;
    font-size: 7.25rem;
    width: 1000px;
  color: #156669;}
  #pSectionTwo{  
     font-size: 2.3rem;
    width: 900px;
    margin: 10px;
    
    font-family: $ff-sans-serif;
    color: #55AD9B;}
    h3{color: #156669;
      margin-top: 0px;}
  #sectionTwo{ display: flex;
  justify-content: flex-start;}
  blockquote {
    position: relative;
    padding-left: 1.5rem;
    font-family: $ff-serif;
    font-size: 2rem;
    line-height: 1.25;
    letter-spacing: -0.05rem;
  
    &:before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 6px;
      height: 100%;
      background-color: $color-accent;
      border-radius: 60px;
    }
  }
  
  figure {
    display: flex;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-size: cover;
  }
  .hero {
  position: relative;
  width: 100vw;
  height: 100vh;

  @each $color in ( #F1F8E8,#D8EFD3, #95D2B3, #55AD9B) {
    $i: index(( #F1F8E8,#D8EFD3, #95D2B3, #55AD9B), $color);
    &:nth-child(#{$i}) figure {
      background-color: $color;
      
    }
  }
}

  .hero-img {
  max-width: 600px;
  margin-right: 1rem;
  margin-top: 50px;
}
.hero-img2 {
  width: 500px;
  margin-left: 4rem;
}

.gallery {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-evenly;
  padding: 0;
  margin: 00px;
  align-items: center;
  width: 100%;
  img {
    display: block;
    max-width:500px;
    margin: 0 auto;
    border-radius: 5px;
    height: 400px;
  }
  p {
    text-align: center;
    font-family: $ff-serif;
    margin-top: 0.9rem;
    color: #156669;
    font-size: 2.6rem;
  }
}

#galleryContainer{
  display: flex;
  flex-direction: column;
  width: 100%;
}
  
  .hero-inner {
    position: absolute;
    overflow: hidden;
    width: 100%;
    height: 100%;
    clip: rect(0, auto, auto, 0);
  
    @supports (-webkit-overflow-scrolling: touch) {
      clip: unset;
      clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
    }
  }
  
  .hero__title {
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    color: white;
    font-family: $ff-serif;
    font-size: 8vw;
    letter-spacing: -0.125rem;
    text-align: center;
  
    @media (min-width: 1200px) {
      font-size: 6rem;
    }
  }
  
  .content {
    position: relative;
    margin: 0 auto 8rem;
    padding: 2rem;
  
    &:before {
      content: "";
      display: block;
      position: absolute;
      top: -100px;
      left: 0;
      width: 100%;
      height: 100px;
      background-color: white;
      z-index: 99;
      clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
    }
  }
  
  .content__inner {
    margin: 0 auto;
    max-width: 700px;
  
    > * + * {
      margin-top: 1.5rem;
    }
    > blockquote {
      margin: 3rem 0;
    }
  }
  
  .content__title {
    font-family: $ff-serif;
    font-size: 4rem;
    line-height: 1.25;
    letter-spacing: -0.125rem;
    text-align: center;
  
    @media (min-width: 600px) {
      font-size: 5rem;
    }
  }
  
  .content__author {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 4rem;
    width: 100%;
    font-family: $ff-serif;
    font-size: 2rem;
    letter-spacing: -0.125rem;
    text-align: center;
  
    &:before,
    &:after {
      content: "";
      flex: 1;
      height: 2px;
      background-color: $color-accent;
    }
  
    &:before {
      margin-right: 1rem;
    }
    &:after {
      margin-left: 1rem;
    }
  }
  </style>
  