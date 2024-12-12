<template>
    <header :class="{ hidden: isHidden }">
    <div class="containerHeader">
    
      <div>
            <img src="/assets/LOGOSANATAKER.png" alt="LOGO">
      </div>
      </div>
    </header>
    <main>
        <section id="section1">
          <h1>Delegar puede ser una forma sencilla de encontrar paz mental </h1>
          <img src="/assets/intro-illustration_qneuer.svg" alt="">
        </section>
        <section id="section2">
            <h3>Sobre mi</h3>
            <div id="sobremi"><img src="/assets/JULI-removebg-preview.png" alt="">
                <p>Hola, soy Juli creadora de Sanatasker. Este proyecto surge de la idea de ayudarte a aliviar el peso de vivir con una enfermedad crónica o acompañar a alguien en esta situación, de modo que la responsabilidad que esto implica no sea una carga adicional en tu vida, ni en la de quienes te rodean. Mi compromiso es brindarte apoyo desde la organización y la empatía para centrarte en lo que realmente importa y sentirte tranquilo en cada paso del camino.</p>
                
            </div>
        </section>
        <section id="section3">
            <h3>Servicios</h3>
            <img src="/assets/Woman working on computer and having phone conversation.png" alt="">
            <p>Facilitar tramites con obras sociales</p>
            <img src="/assets/Girl stands near huge calendar.png" alt="">
            <p>Gestion y organizacion de turnos </p>
            <img src="/assets/Girl with a Letter.png" alt="">
            <p>Recordatorios </p>
        </section>
        <section id="section4">
            <h3>Testimonios</h3>
            <img src="/assets/agos.png" alt="">
           
            <p>Descubrir que tenía una enfermedad crónica rara fue un golpe inesperado. En un momento crítico, Sanatasker (o Juli, como la llamo) me ayudó a organizar mi caótica agenda médica con empatía y dedicación. Gracias a su apoyo, hoy puedo enfocarme en ser feliz, más allá de mi enfermedad.</p>
             <h5>Agostina<span>- Diagnostico, enfermedad inflamatoria intestinal</span></h5>
        </section>
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
        <a href="https://www.instagram.com/sanatasker/" target="_blank"><img src="/assets/icons/instagramverde.png" alt=""></a>
        <a href="https://www.linkedin.com/in/julieta-aranda-ruth/" target="_blank"><img src="/assets/icons/linkedinverde.png" alt=""></a>
        <a href="https://wa.link/7mp5ai" target="_blank"><img src="/assets/icons/whatsappverde.png" alt=""></a>
      </div>
    </div>
        </article>
      </section>
    </main>
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
  
  <style lang="scss"scoped >
  $ff-serif: 'Roca One Thin', serif;
  $ff-sans-serif: 'Roboto', sans-serif;
  $color-accent: #a9dfbf;
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

    @font-face {
      font-family: 'Roca One Thin';
      src: url('../fonts/roca-one-thin.ttf') format('truetype');
      font-weight: normal;
      font-style: normal;
    }
  h5{ font-family: 'Roca One Thin';
  color: #D8EFD3;
  font-size: 2rem;}
  header {
    display: flex;
    justify-content: center;
    padding: 1rem;
    background-color: rgba(85, 173, 155, 0.8); /* Fondo semi-transparente */
    color: white;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    z-index: 1000; /* Asegura que esté sobre todo */

  }
  
  .containerHeader{display: flex;
 
  flex-direction: column;
  align-items: center;}
  .logonone{display: none;}

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
  #section1{display: flex;
flex-direction: column;
flex-wrap: nowrap;
padding: 2%;
background-color:#D8EFD3 ;
}
  #section1 h1{
    text-align: center;
    font-size: 4rem;
    color: #156669;
    font-family:'Roca One Thin';
    font-weight: 300;
  }
  video{border-radius: 10px;
margin: 15px;
margin-bottom: 50px;}
  #section2{display: flex;
flex-direction: column;
flex-wrap: nowrap;
padding: 2%;
background-color:#D8EFD3 ;
align-items: center;

}
#sobremi{align-items: center;
text-align: center;}
#sobremi p{color: #55AD9B;
font-size: 1.5rem;
padding: 0% 15% 0% 15%;


}
#sobremi img{margin-bottom: 25px;}
#section3 h3{    text-align: center;
    font-size: 4rem;
    margin: 25px;
    color: #156669;
    font-family:'Roca One Thin';}
    #section2 h3{    text-align: center;
    font-size: 4rem;
    margin: 25px;
    color: #156669;
    font-family:'Roca One Thin';}
    #section4 h3{    text-align: center;
    font-size: 4rem;
    margin: 25px;
    color: #156669;
    font-family:'Roca One Thin';}
#section3{display: flex;
flex-direction: column;
flex-wrap: nowrap;
align-items: center;
padding: 2%;
background-color: #D8EFD3 ;
}
#section3 img{width: 250px;
}
#section3 p{font-size: 1.5rem;
    color: #156669;
    font-family:'Roca One Thin';
font-weight: 800;}
 #section4{display: flex;
flex-direction: column;
flex-wrap: nowrap;
padding: 2%;
align-items: center;
background-color:#D8EFD3 ;
}
#section4 img{width: 70%;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}
#section4 p{font-size: 1.5rem;
    color: #156669;
font-weight: 800;
    font-family:'Roca One Thin';
background-color: #F1F8E8 ;;
padding: 5%;
width: 70%;
border-bottom-left-radius: 10px;
border-bottom-right-radius: 10px;}
h5{text-align: center;
font-size: 1.4rem;
width: 70%;}

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
.content__author{color: #156669;}
@media (max-width: 520px) {
.content__title{font-size: 2.5rem;}
.content__author{font-size: 1.5rem;}

#section2 img{width: 280px;}
}
#section1 h1{font-size: 3.8rem;}
@media (max-width: 395px) {
.content__title{font-size: 2.5rem;}
.content__author{font-size: 1.5rem;}
#section3 img{width: 200px;
}
#section3 p{font-size: 1.1rem;
    color: #156669;
    font-family:'Roca One Thin';
font-weight: 800;}
#section2 img{width: 280px;}
#section2 p{font-size: 1.4rem;
padding: 0% 5% 0% 5%;}
#section4 p{font-size: 1.2rem;
width: 90%;}
#section4 img{font-size: 1.2rem;
    width: 90%;}
    #section3 h3{    text-align: center;
    font-size: 3.2rem;
    margin: 25px;
    color: #156669;
    font-family:'Roca One Thin';}
    #section2 h3{    text-align: center;
    font-size: 3.2rem;
    margin: 25px;
    margin-bottom: 0px;
    color: #156669;
    font-family:'Roca One Thin';}
    #section4 h3{    text-align: center;
    font-size: 3.2rem;
    margin: 25px;
    color: #156669;
    font-family:'Roca One Thin';}
    #section1 h1{font-size: 3rem;}

}

  </style>
  