<template>
  <div id="about">
    <NavbarComponent />
    <h1 class="title">This is an about page</h1>
  </div>
</template>

<script>
import NavbarComponent from '@/components/NavbarComponent.vue';

export default {
  name: 'AboutView',
  components: { NavbarComponent },
};
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
h1 {
  margin-top: 8rem;
  display: flex;
  justify-content: center;
}
</style>
