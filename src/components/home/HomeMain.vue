<template lang="html">
  <div class="main">
    <Splide :options="options">
      <SplideSlide>
        <div class="img img_one">
          <div class="container">
            <p>Premium quality liquid dish wash Your Kitchen cleaning expert</p>
          </div>
        </div>
      </SplideSlide>
      <SplideSlide>
        <div class="img img_two">
          <div class="container">
            <p>Innovative, Safe and Effective liquid detergents</p>
          </div>
        </div>
      </SplideSlide>
      <SplideSlide>
        <div class="img img_three">
          <div class="container">
            <p>Mosturizing BQHANDWASH. Germs away in seconds</p>
          </div>
        </div>
      </SplideSlide>
    </Splide>
  </div>
</template>
<script>
import { Splide, SplideSlide } from "@splidejs/vue-splide";
import "@splidejs/splide/dist/css/splide.min.css";
import "@splidejs/splide/dist/css/themes/splide-skyblue.min.css";
import { defineComponent } from "vue";
export default defineComponent({
  name: "HomeMain",
  components: {
    Splide,
    SplideSlide,
  },
  data() {
    return {
      options: {
        type: "loop",
        drag: false,
        focus: "center",
        perPage: 1,
        easing: "ease",
        autoplay: true,
        interval: 2000,
        arrows: false,
      },
    };
  },
});
</script>
<style lang="scss" scoped>
@import "@/scss/style.scss";

.main {
  margin-top: 78px;
  width: 100%;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .img {
    height: 500px;
    height: 300px;
    p {
      @include font(20px, 700, 1, $red);
      text-shadow: 2px 2px 2px #692d1e;
      padding: 5rem 0;
    }
  }
  .img_one {
    background: url("../../assets/img/bg-01.svg") no-repeat center center/cover;
  }
  .img_two {
    background: url("../../assets/img/bg-02.svg") no-repeat center center/cover;
  }
  .img_three {
    background: url("../../assets/img/bg-03.svg") no-repeat center center/cover;
  }
}

@media screen and (min-width: 700px) {
  .main {
    .img {
      height: calc(100vh - 78px);
    }
  }
}
</style>
