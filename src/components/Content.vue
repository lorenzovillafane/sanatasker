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
            <template v-if="section.type === 'text-image'">
              <img :src="section.image" alt="Imagen hero" class="hero-img" />
              <p>{{ section.text }}</p>
            </template>
            <template v-else-if="section.type === 'gallery'">
              <div class="gallery">
                <div v-for="(item, idx) in section.items" :key="idx">
                  <img :src="item.image" :alt="item.title" />
                  <p>{{ item.title }}</p>
                </div>
              </div>
            </template>
            <template v-else-if="section.type === 'testimonial'">
              <blockquote>{{ section.quote }}</blockquote>
              <img :src="section.image" alt="Imagen hero" class="hero-img" />
              <p>{{ section.author }}</p>
            </template>
          </div>
        </div>
      </section>
  
      <!-- Sección de contenido original -->
      <section class="content">
        <article class="content__inner">
          <h1 class="content__title">Some Happy Little Text</h1>
          <h3 class="content__author">By Bob Ross</h3>
  
          <p>
            A thin paint will stick to a thick paint. The shadows are just like
            the highlights, but we're going in the opposite direction. When you
            do it your way you can go anywhere you choose.
          </p>
  
          <blockquote>When you do it your way you can go anywhere you choose.</blockquote>
  
          <p>
            Let's build some happy little clouds up here. Everyone is going to
            see things differently - and that's the way it should be. Let's do
            that again. A tree needs to be your friend if you're going to paint
            him. That's why I paint - because I can create the kind of world I
            want - and I can make this world as happy as I want it.
          </p>
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
            type: "text-image",
            image: "src/assets/JULI.png",
            text: "Texto diferente junto a la segunda imagen.",
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
  
  * {
    box-sizing: border-box;
  }
  
  p {
    font-family: $ff-sans-serif;
    font-size: 1.25rem;
    line-height: 1.5;
  }
  
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
}

.gallery {
  display: flex;
  justify-content: space-around;
  align-items: center;
  img {
    display: block;
    max-width:400px;
    margin: 0 auto;
    border-radius: 5px;
  }
  p {
    text-align: center;
    margin-top: 0.5rem;
  }
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
    padding: 0 1rem;
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
    font-size: 3rem;
    line-height: 1.25;
    letter-spacing: -0.125rem;
    text-align: center;
  
    @media (min-width: 600px) {
      font-size: 4rem;
    }
  }
  
  .content__author {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 4rem;
    width: 100%;
    font-family: $ff-serif;
    font-size: 1.5rem;
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
  