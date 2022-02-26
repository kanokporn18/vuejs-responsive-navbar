<template>
  <div class="home">
    <NavbarComponent />

    <section class="home" id="home">
      <div class="home_container container grid">
        <div class="home_data">
          <h1 class="home_title">VUE JS</h1>
          <h2 class="home_subtitle">
            The progressive <br />
            JavaScript Framework.
          </h2>
        </div>
        <img
          src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/2367px-Vue.js_Logo_2.svg.png"
          alt=""
          class="home_img"
        />
      </div>
    </section>
  </div>
</template>

<script>
import NavbarComponent from '@/components/NavbarComponent.vue';

export default {
  name: 'HomeView',
  components: {
    NavbarComponent,
  },
};
</script>
<style scoped>
.home_title {
  font-size: var(--biggest-font-size);
  color: var(--first-color);
  margin-bottom: var(--mb-1);
}

.home_subtitle {
  font-size: var(--h1-font-size);
  color: var(--title-color);
  margin-bottom: var(--mb-4);
}
.home_img {
  width: 300px;
  justify-self: center;
}
</style>
