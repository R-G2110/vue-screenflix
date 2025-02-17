<script>
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
  setup() {
    return {
      modules: [Navigation],
    };
  },
  created() {},
  data() {
    return {};
  },
  props: {},
  methods: {},
};
</script>

<template>
  
  <div class="collection">
    <h2>Catalogo Anime</h2>
    <h5>Catalogo descrizione</h5>
  </div>
  <swiper
    :slidesPerView="5"
    :freeMode="true"
    :navigation="true"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
        <!-- Overlay con altri elementi -->
        <div class="anime-item-overlay">
          <div class="overlay-content">
            <p>Ulteriori dettagli qui!</p>
            <button>Vedi di più</button>
          </div>
        </div>
      </div>
    </swiper-slide>
    <swiper-slide>
      <div class="anime-item">
        <img src="" alt="Nome Anime 1">
        <h3>Nome Anime 01</h3>
        <p>Descrizione breve dell'anime. Un'avventura emozionante che ti terrà incollato allo schermo!</p>
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
    //color: var(--color-gray-light);
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
    padding: 0 10px;  /* Spazio tra gli item */
  }

  /* Le frecce di navigazione devono essere fuori dal carosello */
  .swiper-button-next, .swiper-button-prev {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 40px;
    height: 40px;
    background-color: rgba(0, 0, 0, 0.5);
    border-radius: 50%;
    z-index: 10;
  }

  /* Spostiamo le frecce fuori dal contenitore */
  .swiper-button-next {
    right: -50px; /* Posiziona la freccia "next" più a destra */
  }

  .swiper-button-prev {
    left: -50px; /* Posiziona la freccia "prev" più a sinistra */
  }

  /* Aggiungere hover per migliorare l'interazione */
  .swiper-button-next:hover, .swiper-button-prev:hover {
    background-color: rgba(0, 0, 0, 0.8);
  }

  /* Animazioni per gli item */
  .anime-item {
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    overflow: hidden;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    margin: 0 0 0 40px;  /* Distanza tra gli items */
    position: relative;  /* Aggiunto per il posizionamento dell'overlay */
    cursor: pointer;
  }

  /* Overlay - inizialmente nascosto */
  .anime-item-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5);  /* Colore del lay-over semi-trasparente */
    opacity: 0;  /* Inizialmente invisibile */
    display: flex;
    justify-content: center;
    align-items: center;
    transition: opacity 0.3s ease;
    z-index: 2;  /* L'overlay sarà sopra l'immagine */
  }

  /* Mostriamo l'overlay quando l'elemento è in hover */
  .anime-item:hover .anime-item-overlay {
    opacity: 1;  /* Mostra il lay-over */
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
    height: 200px;
    object-fit: cover;
  }

  .anime-item h3 {
    font-size: 1.2rem;
    color: #333;
    padding: 10px;
    margin: 0;
  }

  .anime-item p {
    padding: 10px;
    font-size: 1rem;
    color: #666;
    position: relative;  /* Assicuriamoci che il testo sia sopra l'overlay */
    z-index: 3;
  }

</style>