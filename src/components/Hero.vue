<script>
import { store } from "../data/store";
import { defineComponent } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";
import "swiper/css/effect-fade";
import { Autoplay, EffectFade, Navigation, Pagination } from "swiper/modules";

export default defineComponent({
  name: "Hero",
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Autoplay, EffectFade, Navigation, Pagination],
    };
  },
  data() {
    return {
      store,
    };
  },
  computed: {
    movies() {
      return this.store.movie || []; // Assicura che sia sempre un array
    },
  },
  mounted() {
    console.log("Movies:", this.store.movie);
  },
});
</script>

<template>
  <div class="hero">
    <swiper
      v-if="movies.length"
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
      <swiper-slide v-for="item in movies" :key="item.id">
        <img
          v-if="item.backdrop_path"
          :src="`https://image.tmdb.org/t/p/original${item.backdrop_path}`"
          :alt="item.title"
        />
        <!-- <img v-else src="/fallback-image.jpg" alt="Fallback Image" /> -->
      </swiper-slide>
    </swiper>
    <p v-else>Loading movies...</p>
  </div>
</template>

<style lang="scss">
.hero {
  margin-top: var(--header-height);
  margin-bottom: 100px;
  border-bottom: 10px solid var(--border-color-dark);
  height: calc(100vh - (var(--header-height) / 2));
}

.swiper-pagination {
  position: absolute;
  bottom: 400px !important;
  left: 100px !important;
  transform: translateX(-40%);
}

.swiper-pagination-bullet {
  background: var(--color-black) !important;
  border: 1px solid var(--color-white) !important;
  transition: background 0.7s ease, width 0.7s ease, border-radius 0.3s ease;
}

.swiper-pagination-bullet-active {
  background: var(--color-red) !important;
  border: none !important;
  width: 200px !important;
  border-radius: 20px;
}
</style>
