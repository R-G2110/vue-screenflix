<script>
import axios from "axios";
import { store } from "../../data/store";

import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import { Navigation } from 'swiper/modules';

export default {
  name: "Collection",
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    type: String, 
  },
  data() {
    return {
      items: [], 
    };
  },
  async created() {
    try {
      const response = await axios.get(`${store.apiUrlBase}${store.default}`, {
        params: {
          ...store.apiParams,
        },
      });

      // Filtra i dati in base alla tipologia (movie o tv)
      this.items = response.data.results.filter((item) => item.media_type === this.type);
    } catch (error) {
      console.error("Errore nel recupero dei dati:", error);
    }
  },
  setup() {
    return {
      modules: [Navigation],
    };
  },
};
</script>

<template>
  <div class="collection">
    <h2>{{ type === 'movie' ? 'Latest Movies' : 'Latest TV Series' }}</h2>
    <h5>Discover the latest</h5>
  </div>
  <swiper
    :slidesPerView="5"
    :freeMode="true"
    :navigation="true"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide v-for="item in items" :key="item.id">
      <div class="anime-item">
        <img :src="'https://image.tmdb.org/t/p/w500' + item.poster_path" :alt="item.title || item.name">
        <h3>{{ item.title || item.name }}</h3>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>

<style lang="scss" scoped>
.collection {
  padding-top: 100px;
  margin-bottom: 50px;
  margin-left: 50px;
  h2 {
    font-size: var(--font-lg);
  }
}

/* Posizionamento corretto dei contenuti */
.swiper-wrapper {
  display: flex;
  justify-content: center;
}

.swiper-slide {
  display: flex;
  justify-content: center;
  padding: 0 10px; /* Spazio tra gli item */
}

/* Stile delle frecce di navigazione */
.swiper-button-next, .swiper-button-prev {
  display: flex !important; /* Forza la visibilità */
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 40px;
  height: 40px;
  background-color: rgba(0, 0, 0, 0.5);
  border-radius: 50%;
  z-index: 10;
}

.swiper-button-next {
  right: -50px; /* Posiziona la freccia "next" più a destra */
}

.swiper-button-prev {
  left: -50px; /* Posiziona la freccia "prev" più a sinistra */
}

.swiper-button-next:hover, .swiper-button-prev:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Animazioni per gli item */
.anime-item {
  width: 300px; /* Larghezza fissa */
  height: 475px; /* Altezza fissa */
  //background-color: #fff;
  //color: var(--color-white);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  cursor: pointer;
}

/* Overlay - inizialmente nascosto */
.anime-item-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: opacity 0.3s ease;
  z-index: 2;
}

/* Mostriamo l'overlay quando l'elemento è in hover */
.anime-item:hover .anime-item-overlay {
  opacity: 1;
}

/* Stili per i contenuti dentro l'overlay */
.overlay-content {
  color: white;
  text-align: center;
}

.overlay-content p {
  margin-bottom: 10px;
  font-size: 1.2rem;
}

.overlay-content button {
  padding: 10px 20px;
  background-color: #ff4081;
  border: none;
  color: white;
  font-size: 1rem;
  cursor: pointer;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.overlay-content button:hover {
  background-color: #f50057;
}

/* Le immagini all'interno degli items */
.anime-item img {
  width: 100%;
  height: 400px;
  object-fit: cover;
}

.anime-item h3 {
  margin: 0;
}
</style>
