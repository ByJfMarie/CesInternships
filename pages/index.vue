<template>
  <div class="home">
    <navbar />
    <div class="top-banner">
      <div class="caroussel">
        <div class="swiper-container">
      <!-- Additional required wrapper -->
      <div class="swiper-wrapper">
          <!-- Slides -->
          <div class="swiper-slide"><img src="https://uproer.com/wp-content/uploads/2017/06/pixels-to-inches-image.jpg" alt=""></div>
          <div class="swiper-slide">Slide 2</div>
          <div class="swiper-slide">Slide 3</div>
          ...
      </div>
      <!-- If we need pagination -->
      <div class="swiper-pagination"></div>

      <!-- If we need navigation buttons -->
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>

      <!-- If we need scrollbar -->
      <div class="swiper-scrollbar"></div>
  </div>
      </div>
      <div class="text-container">
        <p>Ici mettre des renseignements sur le site</p>
      </div>
    </div>
    <hr />
    <h1>Voir toutes les offres >></h1>
    <div class="bottom-banner">
      <div v-for="data in cardData" class="card">
        <div class="card-top">
          <div class="card-img">
            <img :src="data.img" alt="" />
          </div>
          <div class="card-competence">
            <ul class="list-container">
              <li v-for="competence in data.competences" class="list">
                {{ competence }}
              </li>
            </ul>
          </div>
        </div>
        <div class="card-bottom">
          <div class="card-description">
            <h3>Description du poste</h3>
            <p>{{ data.description }}</p>
          </div>
          <div class="card-button">
            <button>Voir plus</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/navbar.vue';
// @ is an alias to /src

  // Import Swiper Vue.js components
  // import { Swiper, SwiperSlide } from 'swiper/vue';
  // import SwiperCore, { Scrollbar, Navigation, EffectFade, Autoplay} from 'swiper';

  import Swiper, { Navigation, Pagination } from 'swiper'
  import 'swiper/swiper-bundle.css'

  Swiper.use([ Navigation, Pagination ])

  // // Import Swiper styles
  // import 'swiper/swiper.scss';
  // import 'swiper/components/navigation/navigation.scss';
  // import 'swiper/components/scrollbar/scrollbar.scss';
  // import 'swiper/components/effect-fade/effect-fade.scss';

  // SwiperCore.use([Scrollbar, Navigation, EffectFade, Autoplay]);

const cardData = [
  {
    id: 1,
    description:
      "Ici y'a la description de l'offre Ici y'a la description de l'offre Ici y'a la description de l'offre",
    img: "https://assets-jpcust.jwpsrv.com/thumbnails/2yzd2pt3-1920.jpg",
    competences: [
      "Angular",
      "React",
      "React",
      "VueJS",
      "UX/UI",
      "React",
      "React",
    ],
  },
  {
    id: 2,
    description: "Ici y'a la description de l'offre",
    img: "https://assets-jpcust.jwpsrv.com/thumbnails/2yzd2pt3-1920.jpg",
    competences: ["Angular", "React"],
  },
  {
    id: 3,
    description: "Ici y'a la description de l'offre",
    img: "https://assets-jpcust.jwpsrv.com/thumbnails/2yzd2pt3-1920.jpg",
    competences: ["Angular", "React"],
  },
];

export default {
  name: "Home",
  mounted() {
    new Swiper('.swiper-container', {
      loop: true,
      pagination: {
        el: '.swiper-pagination',
      },
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      scrollbar: {
        el: '.swiper-scrollbar',
      },
    })
  },
  components: {
    Navbar
    // Swiper,
    // SwiperSlide,
  },
  data() {
    return {
      cardData,
    };
  },
  methods: {
    // onSwiper(swiper) {
    //   console.log(swiper);
    // },
    // onSlideChange() {
    //   console.log('slide change');
    // },
  },
};
</script>

<style lang="scss">
@import "../assets/style/home.scss";
@import "assets/style/app.scss";
</style>
