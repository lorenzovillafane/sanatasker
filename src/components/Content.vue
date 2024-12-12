<template>
   <header :class="{ hidden: isHidden }">
  <div class="containerHeader">
    <div class="socialContainer"> 
  <a href="https://www.instagram.com/sanatasker/"><img src="" alt="" ></a>
   <a href="https://www.linkedin.com/in/julieta-aranda-ruth/" target="_blank"><img src="" alt=""class="logonone"></a>
   <a href="https://wa.link/7mp5ai" target="_blank"><img src="" alt=""class="logonone"></a></div>

    <div>
          <img src="../assets/LOGOSANATAKER.png" alt="LOGO">
    </div>

  <div class="socialContainer">
    <div>
      <h5>Encontrame en</h5>
    </div>
    <div>

    </div>
    <a  href="https://www.instagram.com/sanatasker/" target="_blank"><img src="../assets/icons/instagram-50.png" alt=""></a>
   <a href="https://www.linkedin.com/in/julieta-aranda-ruth/" target="_blank"><img src="../assets/icons/icons8-linkedin-50.png" alt=""></a>
   <a href="https://wa.link/7mp5ai" target="_blank"><img src="../assets/icons/icons8-whatsapp-50.png" alt=""></a>
  </div>
   
    </div>
  </header>
    <div>
      <!-- Sección Hero modificada -->
      <section
        v-for="(section, index) in heroSections"
        :key="index"
        class="hero"
      >
        <div class="hero-inner">
          <figure id="background"></figure>
          <div class="hero__title">
            <template v-if="section.type === 'text-video'" id="sectionVideo">
              <img src="../assets/splashgreen.png" id="splashgreen" alt="">
            <video 
              :src="section.video" 
              controls
             
              class="hero-video"
            ></video>
            <p id="pSectionVideo">{{ section.text }}</p>
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
            <div  id="testimoniosContainer">
              <h3>Testimonios</h3> 
              <figure class="snip1197">
                <figcaption>
         <blockquote>{{ section.quote }}</blockquote>
    <div class="arrow"></div>
  </figcaption>
              <img :src="section.image" alt="Imagen hero" class="hero-img3" />
              <div class="author">
      <h5>{{ section.author }}<span>- Diagnostico, enfermedad inflamatoria intestinal</span></h5>
  </div>
</figure>
            </div> 
         
              
            
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
      
      <form action="https://formsubmit.co/ajulietaruth@gmail.com" method="POST">
        <input type="text" name="name" placeholder="Nombre" />
        <input type="email"  name="email" placeholder="Tu correo" />
        <textarea placeholder="Introduzca un mensaje"></textarea>
        <button type="submit">Enviar</button>
        <input type="submit" value="Enviar">
        <input type="hidden" name="_next"value="http://localhost:8000">
      </form>
      <div class="footer__socials">
        <a href="https://www.instagram.com/sanatasker/" target="_blank"><img src="../assets/icons/instagramverde.png" alt=""></a>
        <a href="https://www.linkedin.com/in/julieta-aranda-ruth/" target="_blank"><img src="../assets/icons/linkedinverde.png" alt=""></a>
        <a href="https://wa.link/7mp5ai" target="_blank"><img src="../assets/icons/whatsappverde.png" alt=""></a>
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
            type: "text-video",
            video: "src/assets/juli2.mp4",
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
              { image: "src/assets/Girl stands near huge calendar.png", title: "Gestion y organizacion de turnos" },
              { image: "src/assets/Girl with a Letter.png", title: "Recordatorios" },
              { image: "src/assets/Woman working on computer and having phone conversation.png", title: "Facilitar tramites con obras sociales" },
            ],
          },
          {
            type: "testimonial",
            image: "src/assets/agos.png",
            quote: "Descubrir que tenía una enfermedad crónica rara fue un golpe inesperado. En un momento crítico, Sanatasker (o Juli, como la llamo) me ayudó a organizar mi caótica agenda médica con empatía y dedicación. Gracias a su apoyo, hoy puedo enfocarme en ser feliz, más allá de mi enfermedad.",
            author: "- Agostina",
          },
        ],
      };
    },
  };
  </script>
  
  <style lang="scss" scoped>


/*HEADER*/
@font-face {
    font-family: 'Roca One Thin';
    src: url('../fonts/roca-one-thin.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
  }
h5{ font-family: 'Roca One Thin';
color: #156669;
font-size: 2rem;}
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

.containerHeader{display: flex;
justify-content: space-between;
align-items: center;}
.logonone{display: none;}
.socialContainer{width: 300px;}
header img {
  margin: 0;
width: 120px;
}
a img{width: 40px;
margin-left: 15px;
margin-top: 15px;
margin-right: 15px;}
a img{

border-radius: 4px;

cursor: pointer;


transition: all 0.2s ease-in-out;
}
a img:hover {
transform: scale(1.1);
}
  /* --------------------
     Fuentes y Variables
  -------------------- */
  @font-face {
    font-family: 'Roca One Thin';
    src: url('../fonts/roca-one-thin.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
  }
  
  $ff-serif: 'Roca One Thin', serif;
  $ff-sans-serif: 'Roboto', sans-serif;
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
  
  /* --------------------
     Estilo Global
  -------------------- */
  * {
    box-sizing: border-box;
    font-family: $ff-serif;
   
    
  }
  html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

  
  p {
    font-family: $ff-serif;
    font-size: 2.25rem;
    line-height: 1.5;
  }
  
  h3 {
    color: #156669;
    
  }
  
  /* --------------------
     Estilo del Footer
  -------------------- */
  .footer__form {
    max-width: 600px;
    margin: 0 auto;
    text-align: center;
  
    h2 {
      font-family: $ff-serif;
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
      display: flex;
      justify-content: space-evenly;
  
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
  .footer__socials a img{

border-radius: 4px;

cursor: pointer;


transition: all 0.2s ease-in-out;
}
a img:hover {
transform: scale(1.1);
}
  /* --------------------
     Estilo de Secciones
  -------------------- */
  #pSectionOne {
    margin-top: 50px;
    font-size: 5.25rem;
    width: 1000px;
    color: #156669;
  }
  
  #pSectionTwo {
    font-size: 2.3rem;
    width: 900px;
    margin: 10px;
    font-family: $ff-sans-serif;
    color: #55AD9B;
  }
  
  #sectionTwo {
    display: flex;
    justify-content: flex-start;
  }

  
  /* --------------------
     Testimonios
  -------------------- */
  figure.snip1197 {
    position: relative;
    min-width: 400px;
    max-width: 1200px;
    width: 100%;
    color: #156669;
    text-align: left;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.15);
  }
  
  figure.snip1197 * {
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
  
  figure.snip1197 img {
    float: right;
    width: 25%;
    height: 25%;
    vertical-align: middle;
    border-radius: 0 8px 8px 0;
  }
  
  figure.snip1197 figcaption {
    top: 0;
    bottom: 0;
    left: 0;
    width: 75%;
    position: absolute;
    background-color: #ffffff;
    border-radius: 8px 0 0 8px;
  }
  
  figure.snip1197 blockquote {
    position: relative;
    padding: 25px 50px 25px 50px;
    font-size: 2rem;
    font-weight: 500;
    text-align: left;
    margin: 0;
    line-height: 1.6em;
  }
  
  figure.snip1197 blockquote:before,
  figure.snip1197 blockquote:after {
    font-family: 'FontAwesome';
    content: "\201C";
    position: absolute;
    font-size: 50px;
    opacity: 0.3;
    font-style: normal;
  }
  
  figure.snip1197 blockquote:before {
    top: 25px;
    left: 20px;
  }
  
  figure.snip1197 blockquote:after {
    content: "\201D";
    right: 20px;
    bottom: 0px;
  }
  
  figure.snip1197 .arrow {
    top: 30px;
    left: 100%;
    width: 0;
    height: 0;
    border-left: 0 solid transparent;
    border-right: 25px solid transparent;
    border-top: 25px solid #ffffff;
    margin: 0;
    position: absolute;
  }
  
  figure.snip1197 .author {
    position: absolute;
    top: 100%;
    width: 100%;
    padding: 10px 15px;
    color: #ffffff;
    margin: 0;
    text-transform: uppercase;
  }
  
  figure.snip1197 .author h5 {
    opacity: 0.8;
    margin: 0;
    font-weight: 800;
    color: #F1F8E8;
    font-size: 2rem;
  }
  
  figure.snip1197 .author h5 span {
    font-weight: 100;
    text-transform: none;
    font-family: $ff-sans-serif;
    padding-left: 5px;
  }
  
  #testimoniosContainer {
    display: flex;
    justify-content: center;
    align-self: center;
    flex-direction: column;
    margin-top: -100px;
  }
  
  /* --------------------
     Fondo y Hero
  -------------------- */
  #background {
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
    width: 100%;
    height: 110vh;
  
    @each $color in (#F1F8E8, #D8EFD3, #95D2B3, #55AD9B) {
      $i: index((#F1F8E8, #D8EFD3, #95D2B3, #55AD9B), $color);
      &:nth-child(#{$i}) figure {
        background-color: $color;
      }
    }
  }

  .hero-video {
  width: 30%;
  margin-left: 150px;
  height: auto;
  max-height: 300px; /* Ajusta según tus necesidades */
  border-radius:10px;

}
#splashgreen{position: absolute;
left: 20px;
margin: 0;
padding: 0;
width: 800px;}

#pSectionVideo {
  margin: 50px;
    font-size: 6rem;
    width: 70%;
    font-weight: 300;
    color: #156669;
}
  .hero-img2 {
    width: 500px;
    margin-left: 4rem;
  }
  
  .hero-img3 {
    height: 300px;
    margin-left: 4rem;
  }
  /*CONTROLADOR*/
  .controls {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-top: 10px;

  button {
    padding: 10px 20px;
    background-color: #156669;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;

    &:hover {
      background-color: #0d4d4e;
    }
  }
}
  
  /* --------------------
     Galería
  -------------------- */
  .gallery {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-evenly;
    padding: 0;
    margin: 0;
    align-items: center;
    width: 100%;
    
  
    img {
      display: block;
      max-width: 500px;
      margin: 0 auto;
      border-radius: 5px;
      max-height: 400px;
    }
  
    p {
      text-align: center;
      font-family: $ff-serif;
      margin-top: 0.9rem;
      color: #156669;
      font-size: 2.6rem;
    }
  }
  
  #galleryContainer {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  
  /* --------------------
     Contenido Interno
  -------------------- */
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
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
 
  #sectionVideo{text-align: center;
  align-items: center;
display: flex;
;
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


@media (max-width: 1600px) {
  h3{font-size: 5.5rem;}
.gallery { 
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-evenly;
    padding: 0;
    margin: 0;
    align-items: center;
    width: 100%;
     img {
      display: block;
      max-width: 300px;
      margin: 0 auto;
      border-radius: 5px;
      max-height: 230px;
     
    }
  
    p {
      text-align: center;
      font-family: $ff-serif;
      margin-top: 0.9rem;
      color: #156669;
      font-size: 2rem;
    }}

    /*footer */
    .content {
  position: relative;
  margin: 0 auto 8rem;
  padding: 2rem;

  &:before {
    content: "";
    display: block;
    position: absolute;
    top: -79px;
    left: 0;
    width: 100%;
    height: 80px;
    background-color: white;
    z-index: 99;
    clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
  }
}
}
@media (max-width: 1450px) {
  #pSectionVideo {
  margin: 50px;
    font-size: 5rem;
    width: 70%;
    font-weight: 300;
    color: #156669;
}
  .hero-img2 {
    width: 400px;
    margin-left: 4rem;
  }
  
  .hero-img3 {
    height: 300px;
    margin-left: 4rem;
  }
  #pSectionTwo {
    font-size: 1.8rem;
    width: 800px;
    margin: 10px;
    font-family: $ff-sans-serif;
    color: #55AD9B;
  }
}
@media (max-width: 1270px) {
  #pSectionTwo {
    font-size: 1.7rem;
    width: 600px;
  }
  .hero-img2 {
    width: 350px;
    margin-left: 4rem;
  }
  #pSectionVideo {

    font-size: 4.5rem;

}
#splashgreen{width: 600px;
left: 40px;}

figure.snip1197 blockquote {
    position: relative;
    padding: 25px 50px 25px 50px;
    font-size: 1.8rem;
    font-weight: 500;
    text-align: left;
    margin: 0;
    line-height: 1.6em;
  }
  #testimoniosContainer{align-items:center;}
  figure.snip1197{width: 99%;
}
.gallery p{font-size: 1.8rem;}
}
@media (max-width: 1060px) {
  #pSectionVideo {
  margin: 50px;
    font-size: 3.5rem;
    width: 70%;
    font-weight: 300;
    color: #156669;
}
.hero-img2 {
    width: 250px;
    margin-left: 4rem;
  }


 
  .hero-video {
    width: 30%;
    margin-left: 100px;
    margin-right: auto;
  }

  .hero-img2,
  .hero-img3 {
    
    margin-left: auto;
    margin-right: auto;
  }

  #pSectionVideo,
  #pSectionTwo {
 
    width: 90%;
    margin: 20px auto;
  }

  #sectionTwo {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .gallery {
    flex-wrap: wrap;
    justify-content: space-evenly;

    img {
      max-width: 200px;
      max-height: 150px;
    }

    p {
     
      font-size: 1.7rem;
    }
  }

  figure.snip1197 blockquote {

    font-size: 1.6rem;
  
    line-height: 1.5em;
  }
  figure.snip1197 .author h5 {
    opacity: 0.8;
    margin: 0;
    font-weight: 800;
    color: #F1F8E8;
    font-size: 1.6rem;
  }
 
}
@media (max-width: 950px) {
  figure.snip1197 blockquote {

font-size: 1.4rem;

line-height: 1.5em;
}
figure.snip1197 .author h5 {
    opacity: 0.8;
    margin: 0;
    font-weight: 800;
    color: #F1F8E8;
    font-size: 1.4rem;
  }
}
@media (max-width: 800px) {
  figure.snip1197 blockquote {

font-size: 1.3rem;

line-height: 1.3em;
}
figure.snip1197 .author h5 {
    opacity: 0.8;
    margin: 0;
    font-weight: 800;
    color: #F1F8E8;
    font-size: 1.4rem;
  }

  h3{font-size: 3.5rem;}
  #pSectionTwo {
    font-size: 1.5rem;
 
  }

  
}
@media (max-width: 750px) {
  #sectionVideo{text-align: center;
  align-items: center;
display: flex;
flex-direction: column;}

}


</style>
