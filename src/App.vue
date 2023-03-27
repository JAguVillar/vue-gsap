<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    const texto1 = this.$refs.texto1.offsetWidth;
    const texto2 = this.$refs.texto2.offsetWidth;
    const texto3 = this.$refs.texto3.offsetWidth;
    const total = texto1 + texto2 + texto3
    console.log(texto1, texto2, texto3);
    const tl = gsap.timeline();
    tl.to(".linea", { width: total, opacity: 1, duration: 0 })
      .to(".texto-entradas", { opacity: 1, duration: 0 }, '+=0.5')
      .to(".local", { opacity: 1, duration: 0 }, '+=0.5')
      .to(".visitante", { opacity: 1, duration: 0 }, '+=0.5')
      .to(".home", { height: '95vh' }, '+=0.5')
      .to(".entradas", { height: 'fit-content' })


  },
};
</script>

<template>
  <div class="nav">
  </div>
  <div class="home">
    <img class="estadio" src="./assets/home.webp" alt="" srcset="">
  </div>
  <div class="entradas">
    <div class="equipos">
      <div>
        <span ref="texto1" class="texto-entradas">ENTRADAS </span>
        <span ref="texto2" class="local">CENTRAL - </span>
        <span ref="texto3" class="visitante">BOCA JUNIORS</span>

      </div>
      <div class="linea"></div>
    </div>
    <div class="entradas-bottom">
      <div class="boton">
        COMPRAR AHORA
      </div>
      <img class="nike" src="./assets/nike-partner.webp" alt="">
    </div>
  </div>
  <div class="entradas-invisible">
  </div>
</template>

<style scoped>
.nav {
  height: 128px;

  background: #00009c;
}

.home {

  height: 0vh;
}

.estadio {
  width: 100%;
  height: 100%;
}

.entradas {
  background: #00009c;
  height: 100vh;
  padding: 64px 64px 0px 64px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.equipos {
  font-size: 100px;
  font-weight: 700;
  color: white;
  letter-spacing: -11px;
  text-align: left;
}

.texto-entradas {
  width: fit-content;
  opacity: 0;
}

.local {
  width: fit-content;
  opacity: 0;
}

.visitante {
  width: fit-content;
  opacity: 0;
}

.linea {
  height: 20px;
  opacity: 0;
  background: white;
}

.entradas-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 129px;
}

.boton {
  color: #fff;
  font-size: 18px;
}

.nike {
  height: 54px;
  max-width: 164px;
}
</style>
