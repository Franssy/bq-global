<template>
  <header class="header">
    <div class="container">
      <div class="header-content">
        <div class="logo">
          <router-link to="/"
            ><img src="@/assets/img/logo.png" alt="logo"
          /></router-link>
        </div>
        <nav class="nav" :class="{ open: open }">
          <ul>
            <li v-for="(route, index) in routes" :key="index">
              <router-link :to="{ name: route.name }">{{
                route.title
              }}</router-link>
            </li>
            <li class="cart-wrapper mobile-cart">
              <span class="counter">{{ counter }}</span>
              <span class="mdi mdi-cart cart"></span>
            </li>
          </ul>
        </nav>
        <div class="flex-nav hide-on-lg">
          <div @click="openNav" class="hamburger" :class="{ change: open }">
            <div></div>
            <div></div>
            <div></div>
          </div>
          <div class="cart-wrapper">
            <span class="counter">{{ counter }}</span>
            <span class="mdi mdi-cart cart"></span>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderTag",
  data() {
    return {
      open: false,
      searchBar: false,
      counter: 0,
      routes: [
        {
          name: "home",
          title: "Home",
        },
        {
          name: "about",
          title: "About Us",
        },
        {
          name: "about",
          title: "Products",
        },
        {
          name: "about",
          title: "Become a Distributor",
        },
        {
          name: "about",
          title: "Blog",
        },
        {
          name: "about",
          title: "Resource Center",
        },
      ],
    };
  },
  methods: {
    openNav() {
      this.open = !this.open;
    },
  },
  mounted() {
    this.$router.beforeEach((from, to, next) => {
      this.open = false;
      next();
    });
  },
};
</script>

<style scoped lang="scss">
@import "@/scss/style.scss";
.header {
  position: fixed;
  z-index: 1000;
  top: 0;
  left: 0;
  width: 100%;
  height: 78px;
  background: $white;
  display: flex;
  &-content {
    @include flex(flex, space-between, center, row);
  }
}
img {
  width: 100px;
}
.hamburger {
  display: flex;
  flex-direction: column;
  align-items: end;
  width: 30px;
  height: 20px;
  z-index: 10;
  & > div {
    height: 2px;
    width: 30px;
    background: $pri-color;
    margin: 0.1rem 0;
    transition: transform ease-in-out 0.4s;
    cursor: pointer;
  }
}
.change.hamburger > div:nth-child(1) {
  transform: translate(1px, 5px) rotate(45deg);
}
.change.hamburger > div:nth-child(2) {
  opacity: 0;
}
.change.hamburger > div:nth-child(3) {
  transform: translate(0px, -6px) rotate(-45deg);
}
.open.nav {
  left: 0;
}
.nav {
  position: fixed;
  top: 78px;
  left: -100%;
  width: 100%;
  height: 100%;
  background: $white;
  transition: all ease 0.25s;
  & ul {
    margin-top: 100px;
    list-style: none;
  }
  & ul li {
    display: block;
    padding: 0;
    margin: 0;
  }
  & a {
    display: block;
    text-decoration: none;
    @include font(18px, 500, 30px, $pri-color);
    padding: 1rem;
    text-transform: capitalize;
  }
  & a.router-link-exact-active {
    font-weight: bold;
    color: $white;
    background: $pri-btn;
  }
}

.cart-wrapper {
  position: relative;
  margin-right: 1rem;
  .cart {
    background: #fc0f1d;
    padding: 0.25rem 0.5rem;
    border-radius: 50%;
    @include font(10px, 400, 1, $white);
  }
  .counter {
    background: #f87d24;
    padding: 0.25rem 0.4rem;
    border-radius: 50%;
    @include font(8px, 400, 1, $white);
    position: absolute;
    top: -6px;
    right: 0px;
  }
}
.mobile-cart {
  display: none !important;
}

.flex-nav {
  @include flex(flex, flex-start, center, row);
  gap: 0.5rem;
}
@media screen and (min-width: 1000px) {
  %after {
    position: absolute;
    content: "";
    bottom: 0;
    left: 50%;
    border-radius: 20px;
    transform: translateX(-50%);
    height: 3.5px;
    background: $pri-btn;
    transition: width 0.5s ease-in-out;
  }
  .hamburger {
    display: none;
  }
  .nav {
    position: relative;
    width: auto;
    height: auto;
    background: none;
    z-index: 0;
    top: 0;
    left: 0;
    display: block;
    margin: 0;
    & ul {
      padding: 0;
      margin: 0;
      display: block;
    }
    & ul li {
      display: inline;
    }
    & a {
      @include font(14px, 500, 21px, $nav-color);
      display: inline;
      padding: 0 1rem 0.45rem;
      position: relative;
      transition: all ease 0.5s;
      &::after {
        @extend %after;
        width: 0;
      }
      &:hover::after {
        width: 20px;
      }
      &:hover {
        color: $pri-btn;
      }
    }
    & a.router-link-exact-active {
      color: $pri-btn;
      background: none;
      position: relative;
      &::after {
        @extend %after;
        width: 20px;
      }
    }
  }
  .flex-nav {
    display: none;
  }
  .mobile-cart {
    display: inline-block !important;
  }
}
</style>
