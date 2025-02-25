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
      store,
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
    <h5>Discover the latest {{ type }}</h5>
  </div>
  <swiper
    :slidesPerView="5"
    :spaceBetween="0"
    :freeMode="true"
    :navigation="true"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide v-for="item in items" :key="item.id">
      <div class="item">
        <img :src="'https://image.tmdb.org/t/p/w500' + item.poster_path" :alt="item.title || item.name">
        <p>{{ item.title || item.name }}</p>
        
        <div class="item-overlay">
          <div class="overlay-content">
            <p class="title">{{ item.title || item.name }}</p>
            <p>{{ (item.vote_average / 2).toFixed(1) }}★ ({{ store.formatVoteCount(item.vote_count) }} votes)</p>
            <p class="overview">{{ item.overview }}</p>
          </div>
          <div class="overlay-btn">
            <div class="btn">
              <span class="material-symbols-outlined">play_arrow</span>
              <p>play now</p>
            </div>
            <div class="btn">
              <span class="material-symbols-outlined">add</span>
              <p>add to watchlist</p>
            </div>
          </div>
        </div>
      </div>
    </swiper-slide>
  </swiper>
</template>

<style lang="scss" scoped>
$transition-fast: 0.4s ease-in-out;
$transition-medium: 0.8s ease;
$shadow-light: 0 4px 10px rgba(0, 0, 0, 0.1);
$shadow-hover: 0 10px 20px rgba(0, 0, 0, 0.3);

.collection {
  padding: 100px 0 50px 50px;

  h2 {
    font-size: var(--font-lg);
  }
}

.swiper-slide {
  cursor: pointer;
  display: flex;
  justify-content: center;
}

.swiper-button-next,
.swiper-button-prev {
  display: flex !important;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 30px;
  height: 30px;
  font-weight: 900 !important;
  background-color: rgba(0, 0, 0, 0.5);
  border-radius: 50%;
  z-index: 10;
  border: 5px solid var(--color-red) !important;

  &.swiper-button-next {
    right: -50px;
  }

  &.swiper-button-prev {
    left: -50px;
  }
}

.item {
  width: 300px;
  height: 500px;
  position: relative;
  box-shadow: $shadow-light;
  overflow: hidden;
  cursor: pointer;
  transition: transform $transition-fast, box-shadow $transition-fast, border $transition-fast;

  &:hover {
    border: var(--border-width) solid var(--color-red);
    box-shadow: $shadow-hover;
  }

  &:hover img{
    transform: scale(1.3);
  }
  
  img {
    width: 100%;
    height: 470px;
    transition: transform $transition-medium;

  }
}

.item-overlay {
  position: absolute;
  padding: 0 20px;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.86);
  opacity: 0;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transition: opacity 0.3s ease;
  z-index: 10;

  .title {
    font-size: var(--font-md);
    margin: 20px 0;
  }

  .overview {
    font-size: var(--font-xs);
    margin-bottom: 20px;
    overflow: auto;
  }
}

.item:hover .item-overlay {
  opacity: 1;
}

.overlay-btn {
  display: flex;
  position: absolute;
  bottom: 10px;
  left: 20px;

  .btn {
    display: flex;
    flex-direction: column;
    margin-right: 10px;
    color: var(--color-white);

    span {
      font-size: var(--font-xl);
      color: var(--color-white);
      transition: all $transition-fast;
    }

    p {
      margin-top: -5px;
      font-size: var(--font-xxs);
      transition: all $transition-medium;
    }

    &:hover {
      color: var(--color-red);

      span {
        color: var(--color-red);
      }
    }
  }
}

</style>

