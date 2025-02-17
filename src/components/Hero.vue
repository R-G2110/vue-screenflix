<script>
import { defineComponent } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import 'swiper/css/effect-fade';
import { Autoplay, EffectFade, Navigation, Pagination } from 'swiper/modules';

export default defineComponent({
  name: "Hero",
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Autoplay,EffectFade,Navigation, Pagination],
    };
  }


});
</script>


<template>
  <div class="hero">
    <swiper 
      :autoplay="{
        delay: 5000,
        disableOnInteraction: false,
      }"
      :pagination="{ clickable: true }"
      :navigation="false" 
      :effect="'fade'"
      :modules="modules" 
      :loop="true"
      class="mySwiper"
    >
      <swiper-slide>
        <img src="/Screenshot1.png" alt="">
      </swiper-slide>
      <swiper-slide>
        <img src="/Screenshot2.png" alt="">
      </swiper-slide>
      <swiper-slide>
        <img src="/Screenshot3.png" alt="">
      </swiper-slide>
    </swiper>
  </div>
</template>

<style lang="scss">
.hero {
  margin-top: var(--header-height);
  border-bottom: 1px solid var(--border-color);
  height: 100vh;
}

.swiper-pagination {
  position: absolute;
  bottom: 400px !important; /* Posiziona la paginazione 20px dal basso */
  left: 100px !important; /* Centra la paginazione orizzontalmente */
  transform: translateX(-40%); /* Compensa il 50% della larghezza per centrarla perfettamente */
}


.swiper-pagination-bullet {
  background: var(--color-gray-light) !important;
  transition: background 0.7s ease, width 0.7s ease, border-radius 0.3s ease; 
}

.swiper-pagination-bullet-active {
  background: var(--color-red) !important;
  width: 200px !important;
  border-radius: 20px;
}
</style>

