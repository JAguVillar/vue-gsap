<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    const halfViewportWidth = window.innerWidth / 2
    console.log(halfViewportWidth);
    const box = this.$refs.box;
    const box2 = this.$refs.box2;
    const contenedor = this.$refs.contenedor;
    console.log(box);
    var tl = gsap.timeline();
    ScrollTrigger.create({
      trigger: '.segunda',
      onEnter: () => {
        console.log('pap');
        // tl.to(".card", { opacity: 1, background: 'red', duration: 0.5 });
        // tl.to(".card", { opacity: 1, background: 'green', duration: 0.5 });
        // tl.to(".card", { opacity: 1, background: 'blue', duration: 0.5 });
        // tl.fromTo(".texto-card", { opacity: 0, x: 0 }, { opacity: 1, x: 50 });
        tl.fromTo("img", { opacity: 0, scale: '2' }, { opacity: 1, scale: '1' });
      },
    });
    ScrollTrigger.create({
      trigger: 'h1',
      onEnterBack: () => {
        console.log('pap');
        tl.to(".texto", { background: 'white' });
      },
      onLeave: () => {
        console.log('pap');
        tl.to(".texto", { background: 'red' });
      },
    });
  },
};
</script>

<template>
  <div class="texto">
    <h1>Hola</h1>
  </div>
  <div class="contenedor">
    <div ref="box" class="card primera">
      <h1 class="texto-card">a</h1>
    </div>
    <div ref="box2" class="card segunda">
      <img src="./assets/kindred.jpg" alt="">
    </div>
    <div ref="box3" class="card tercera">
    </div>
  </div>
</template>

<style scoped>
.contenedor {
  width: 100vw;
  opacity: 1;
  display: flex;
  flex-direction: column;

  justify-content: center;
  align-items: center;
}

.texto {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;

}

.card {
  background: #000;
  width: 50vw;
  min-height: 200px;
  border-radius: 25px;
  margin: 20px;
}

img {
  opacity: 0;
  max-width: 50%;
}
</style>
