<template>
  <div class="footer" id="footer">
    <div class="container">
      <div class="footer-content">
        <ul>
          <li><img src="@/assets/img/logo.png" alt="logo" /></li>
          <li class="title">Tel</li>
          <li><a href="tel:+08094488997">0809 448 8997</a></li>
          <li><a href="tel:+08094488995">0809 448 8995</a></li>
          <li class="title">Email</li>
          <li>
            <a href="mailto:hello@bqglobalsolutions.com"
              >hello@bqglobalsolutions.com</a
            >
          </li>
        </ul>
        <ul>
          <li class="title">Customer Service</li>
          <li v-for="service in services" :key="service">
            <router-link :to="{ route: service.name }">{{
              service.title
            }}</router-link>
          </li>
        </ul>
        <ul>
          <li class="title">Company</li>
          <li v-for="company in companies" :key="company">
            <router-link :to="{ route: company.name }">{{
              company.title
            }}</router-link>
          </li>
        </ul>
        <ul>
          <li class="title">Reach Us</li>
          <li class="title">Address</li>
          <li>
            73, college road, beside access bank, <br />
            estate bus stop, college road, ogba Lagos
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "FooterTag",
  data() {
    return {
      services: [
        {
          route: "about",
          title: "Become a Distributor",
        },
        {
          route: "about",
          title: "Ordering and Payment",
        },
        {
          route: "about",
          title: "Returns policy",
        },
        {
          route: "about",
          title: "FAQS",
        },
      ],
      companies: [
        {
          route: "about",
          title: "About BQSafewash",
        },
        {
          route: "about",
          title: "Work with Us",
        },
        {
          route: "about",
          title: "Privacy Policy",
        },
        {
          route: "about",
          title: "Terms and Conditions",
        },
      ],
      socials: [
        {
          route: "facebook",
          icon: "mdi mdi-facebook",
          href: "https://web.facebook.com/companyexpaint",
        },
      ],
    };
  },
};
</script>
<style lang="scss" scoped>
@import "@/scss/style.scss";
.footer {
  background: $white;
  padding: 3rem 0 !important;
  &-content {
    ul {
      margin: 2rem 0 0;
      list-style: none;
      img {
        width: 100px;
      }
      li.title {
        @include font(14px, 700, 21px, $pri-color);
        margin-bottom: 0.5rem;
      }
      li {
        padding: 0.6rem 0 0;
      }
      li a,
      li {
        @include font(12px, 500, 18px, $pri-color);
      }
      li.socials {
        @include flex(flex, flex-start, center, row);
        a {
          padding-right: 0.8rem;
          transition: ease all 0.5s;
          &:hover {
            color: $pri-btn;
          }
        }
      }
    }
  }
  small {
    @include font(12px, 500, 18px, $pri-color);
    display: block;
    margin-top: 3rem;
  }
}

@media screen and (min-width: 700px) {
  .footer {
    &-content {
      @include grid(grid, 2, 1fr, 1rem, 1rem);
      ul {
        margin: 0;
        list-style: none;
        li:first-child {
          @include font(16px, 700, 24px, $pri-color);
        }
        li a,
        li {
          @include font(14px, 500, 21px, $pri-color);
        }
      }
    }
    small {
      @include font(14px, 500, 21px, $pri-color);
    }
  }
}

@media screen and (min-width: 1000px) {
  .footer {
    &-content {
      @include grid(grid, 4, 1fr, 1rem, 1rem);
    }
  }
}
</style>
