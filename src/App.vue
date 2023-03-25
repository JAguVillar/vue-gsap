<script>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    const halfViewportWidth = window.innerHeight;

    const tl = gsap.timeline();
    tl.fromTo(".barra", { yPercent: -100 }, { yPercent: 100, duration: 1 });
    tl.fromTo("h1", { opacity: 0 }, { opacity: 1 });
    // var tl = gsap;
    // tl.fromTo(
    //   ".barra",
    //   { height: 0 },
    //   { height: halfViewportWidth, duration: 1 }
    // );
  },
};
</script>

<template>
  <div class="contenedor">
    <div class="barra negra primera"></div>
    <div class="barra blanca segunda"></div>
    <div class="barra negra tercera">
      <h1>CACC</h1>
    </div>
    <div class="barra blanca cuarta"></div>
    <div class="barra negra quinta"></div>
    <!-- <div class="texto">
      <h1>CACC</h1>
    </div> -->
  </div>
</template>

<style scoped>
.contenedor {
  width: 100vw;
  opacity: 1;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.barra {
  width: 20%;
  height: 0;
}

.negra {
  background-color: #000;
}
.blanca {
  background-color: #fff;
}

.tercera {
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  color: #fff;
}
</style>
