<template lang="html">
  <div class="main">
    <div class="container">
      <h1>Premium quality liquid dish wash Your Kitchen cleaning expert</h1>
    </div>
  </div>
</template>
<script>
export default {
  name: "HomeMain",
};
</script>
<style lang="scss" scoped>
@import "@/scss/style.scss";
.main {
  background: url("../../assets/img/main-bg.svg") no-repeat center center/cover;
  display: flex;
  margin-top: 78px;
  height: calc(100vh - 78px);
  width: 100%;
  & .container {
    @include flex(flex, center, center, column);
    text-align: center;
    h1 {
      @include font(30px, 700, 42px, $red);
    }
    p {
      @include font(18px, 500, 25px, $sec-color);
      margin: 1.5rem 0;
    }
  }
}

@media screen and (min-width: 700px) {
  .main {
  }
}

@media screen and (min-width: 1000px) {
  .main {
  }
}

@media screen and (min-width: 1400px) {
  .main {
  }
}
</style>
