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
  data() {
    return {
      modules: [Autoplay, EffectFade, Navigation, Pagination],
    };
  },
  computed: {
    all() {
      return store.all || [];
    },
    formatVoteCount() {
      return (count) => {
        return count >= 1000 ? (count / 1000).toFixed(1) + "k" : count;
      };
    },
  },
  mounted() {
    console.log("all:", store.all);
  },
});
</script>

<template>
  <div class="hero">
    <swiper
      v-if="all.length"
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
      <swiper-slide v-for="item in all" :key="item.id">
        <img 
          v-if="item.backdrop_path"
          :src="`https://image.tmdb.org/t/p/original${item.backdrop_path}`"
          :alt="item.title"
        />
        <div class="slide-content">
          <h2 class="slide-title">{{ item.title || item.name }}</h2>
          <p>
            {{ item.media_type === "tv" ? "TV series" : "Movie" }}
            <span class="vote-average">{{ (item.vote_average / 2).toFixed(1) }} ★</span>
            <span class="vote-count">({{ formatVoteCount(item.vote_count) }} votes)</span>
          </p>
          
          <div class="content-btn">
            <span class="play-btn">Watch now</span>
            <span class="material-symbols-outlined playlist-btn">
              playlist_add
            </span>
          </div>
        </div>
      </swiper-slide>
      
    </swiper>
  </div>
</template>

<style lang="scss">
.hero {
  position: relative;
  margin-top: var(--header-height);
  margin-bottom: 100px;
  border-bottom: 10px solid var(--border-color-dark);
  height: calc(100vh - (var(--header-height) / 2));
}

.swiper-pagination {
  position: absolute;
  bottom: 550px !important;
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

/* Stili per il titolo sopra l'immagine */
.hero .swiper-slide {
  position: relative;
}

.slide-content {
  padding: 20px;
  width: 30%;
  position: absolute;
  left: 0;
  top: 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  height: 100%;
  background-color: rgba(0, 0, 0, 1);
  z-index: 100;
}

.slide-title { 
  margin-top: 150px;
  font-size: 2rem;
  font-weight: bold;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
}

.vote-average {
  margin-left: 20px;
}
.vote-count {
  margin-left: 5px;
}

.content-btn {
  width: 90%;
  position: absolute; /* Posizionamento fisso relativo a .slide-content */
  bottom: 600px; /* Distanza dal basso */
  left: 40px; /* Allineamento a sinistra */
  display: flex;
  gap: 20px;
}


.play-btn {
  padding: 10px 100px;
  font-weight: 700;
  background-color: var(--color-white);
  cursor: pointer;
  transition: background-color 0.7s ease;
  color: var(--color-red);
  &:hover {
    color: var(--color-gray-dark);
    background-color: var(--color-red);
  }
}

.playlist-btn {
  font-size: var(--font-xl);
  cursor: pointer;
  transition: color 0.7s ease;
  &:hover {
    color: var(--color-red);
  }
}
</style>
