<template>
  <div class="main">
    <div class="container">
      <div class="show-box">
        <button class="show__btn">
          TV shows<img src="../assets/Chevron-Right.png" alt="" />
        </button>

         <div class="movies-slider" v-bind="slickOptions">
          <VueSlickCarousel class="movie-card-box"
        :key="img"
        @click="updateIndexOnClick(i)">
            <div>
              <div>
                <div class="box" v-for="(item, index) in items"
            :key="index">
              <div
            class="new-movie-card"
          >
            <img
              :src="`https://image.tmdb.org/t/p/w500/${item.poster_path}`"
              alt=""
              class="new-movie__img"
            />
            <!-- <div class="movie-info">
              <p class="new-movie__tag">{{ item.genre_ids[0] }}</p>
              <p class="new-movie__rate">Movie rate: {{ item.vote_average }}</p>
              <h3 class="new-movie__title">{{ item.title }}</h3>
            </div> -->
          </div>
            </div>
              </div>
            </div>
          </VueSlickCarousel>
        </div>
      </div>
    </div>
  </div>
</template>

<script>


import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
export default {

  name: "WorksCarousel",
components: { VueSlickCarousel },


data: function () {
    return {
      items: [],
      slides: [
        
      ],
      currentSlide: 0,
      settings: {
  infinite: true,
   slidesToShow: 3,
  slidesToScroll: 3
      },
    };
  },

  watch: {
    currentSlide(newValue) {
      this.$refs.carousel.goTo(newValue);
    },
  },


  methods: {
    
    shows() {
      fetch(
        `https://api.themoviedb.org/3/movie/top_rated?api_key=3f6523220ef2d2a56a4b523bf022b783&language=en-US`
      )
        .then((res) => res.json())
        .then((data) => {
          this.items = data.results;
        });
      console.log(this.items);
    },


    updateIndexOnClick(slideIndex) {
      this.currentSlide = slideIndex;
    },
    updateIndexOnDrag(oldSlideIndex, newSlideIndex) {
      this.currentSlide = newSlideIndex;
    },

  },

  mounted() {
    this.shows()
  },
};


</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700&display=swap");
.show-box {
  max-width: 1320px;
  margin: 0 auto;
  padding: 18px;
  font-family: "Roboto", sans-serif;
}
.show__btn {
  display: flex;
  align-items: center;
  background-color: transparent;
  color: #fff;
  border: none;
  cursor: pointer;
  font-size: 14px;
  margin-left: 15px;
  margin-bottom: 16px;
}

.show-movie__img {
  max-width: 300px;
  width: 100%;
  transition: 0.5s ease-in-out;
}

.show-movie-card {
  position: relative;
  width: 300px;
  height: 445px;
  overflow: hidden;
  cursor: pointer;
}

.show-movie-card:hover .show-movie__img {
  transform: scale(1.1);
}

.movie-info {
  width: 100%;
  height: 100%;
  box-shadow: inset 0px -310px 50px 0px rgb(0 0 0 / 50%);
  position: absolute;
  transform: translate(0%, -100%);
  padding: 285px 0px 15px 25px;
  color: #fff;
}

.show-movie__tag {
  background-color: rgba(44, 44, 44, 0.652);
  padding: 3px 5px;
  font-size: 14px;
  color: #0feffd;
  display: inline;
  font-weight: normal;
  border-radius: 0 5px 0 5px;
}

.show-movie__rate {
  margin: 16px 0;
  font-size: 12px;
}

.show-movie__title {
  font-weight: 500;
  font-size: 24px;
}

.shows-slider {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}
</style>
