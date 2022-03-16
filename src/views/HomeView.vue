<template>
  <div class="home">
    <the-header />
    <home-main />
    <the-footer />
  </div>
</template>

<script>
import TheHeader from "@/components/navbar/TheHeader.vue";
import HomeMain from "@/components/home/HomeMain.vue";
import TheFooter from "@/components/navbar/TheFooter.vue";

export default {
  name: "HomeView",
  components: {
    TheHeader,
    HomeMain,
    TheFooter,
  },
};
</script>
