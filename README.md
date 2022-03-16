# BQ-GLOBAL

<!-- ![banner](./src/assets/img/screenshot.png) -->

## About the project

Premium quality liquid dish wash Your Kitchen cleaning expert

## Tech Stack

**Client:** VueJS, Vuex

**Server:** Golang

### Tools and Cheatsheet

Before running the project locally, make sure the following have been installed:

- Node
- NPM
- Vue 3

Libraries and packages used:

- [Vue](https://vuejs.org/)
- [Vuex](https://vuex.vuejs.org/)
- [Vue Router](https://router.vuejs.org/)
- [Vuelidate](https://vuelidate-next.netlify.app/)
- [Moment](https://momentjs.com/)
- [MDI Fonts](https://materialdesignicons.com/)
- [AOS - Animate On Scroll](https://michalsnik.github.io/aos/)
- [Axios](https://axios-http.com/)
- [Vue Owl Carousel](https://github.com/s950329/vue-owl-carousel)

Useful Links:

- [Figma](https://www.figma.com/file/sLRZTerNf3kUx7hoMCBlTo/BQGLOBAL?node-id=0%3A1)
- [Staging URL](https://bq-global.netlify.app/)
<!-- - [Production URL](https://www.technifyincubator.com/) -->

### Building the app locally

Clone the project

```bash
  git clone https://github.com/bq-global.git
```

Go to the project directory

```bash
  cd bg-global
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run serve
```

### Code Standards

- Folder names should be in `camelCase` e.g `components, getStarted, auth`
- Vue files should be in `PascalCase` e.g `Home.vue, TheFooter.vue, BaseInput.vue`
- Make sure to run `npm run lint` before pushing any code.
- Never use `v-if` on the same element as `v-for`

### VueJS Style

All code must meet the [Style Guide](https://v3.vuejs.org/style-guide/). This makes certain that all code is the same format as the existing code and means it will be as readable as possible.
Any code written otherwise will not be approved.

## Pull Request Checklist

When you submit your pull request, or you push new commits to it, our automated
systems will run some checks on your new code. We require that your pull request
passes these checks, but we also have more criteria than just that before we can
accept and merge it. We recommend that you check the following things locally
before you submit your code:

- It passes tests: run the following command to run all of the tests locally:

  ```
  npm run lint
  ```

- Impacted code has new or updated tests
- Documentation created/updated
- Follows all the code standards required.
