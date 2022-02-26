<template>
  <div class="body">
    <router-view />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap');

:root {
  --header-height: 3rem;

  --first-color: #069c54;
  --title-color: #393939;
  --text-color: #707070;
  --body-color: #fbfefd;

  --body-font: 'Poppins', sans-serif;
  --biggest-font-size: 2.25rem;
  --h1-font-size: 1.5rem;
  --h2-font-size: 1.25rem;
  --h3-font-size: 1rem;
  --normal-font-size: 0.938rem;
  --small-font-size: 0.813rem;
  --smaller-font-size: 0.75rem;

  --font-medium: 500;
  --font-semi-bold: 600;

  --mb-1: 0.5rem;
  --mb-2: 1rem;
  --mb-3: 1.5rem;
  --mb-4: 2rem;
  --mb-5: 2.5rem;
  --mb-6: 3rem;

  --z-tooltip: 10;
  --z-fixed: 100;
}

@media screen and (min-width: 768px) {
  :root {
    --biggest-font-size: 4rem;
    --h1-font-size: 2.25rem;
    --h2-font-size: 1.5rem;
    --h3-font-size: 1.25rem;
    --normal-font-size: 1rem;
    --small-font-size: 0.875rem;
    --smaller-font-size: 0.813rem;
  }
}
*,
::before,
::after {
  box-sizing: border-box;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: var(--header-height) 0 0 0;
  font-family: var(--body-font);
  font-size: var(--normal-font-size);
  background-color: var(--body-color);
  color: var(--text-color);
  line-height: 1.6;
  width: 100%;
  height: 100vh;
}
h1,
h2,
h3,
p,
ul {
  margin: 0;
}

ul {
  padding: 0;
  list-style: none;
}

a {
  text-decoration: none;
}
img {
  max-width: 100%;
  height: auto;
}
.container {
  max-width: 960px;
  width: calc(100% - 2rem);
  margin-left: var(--mb-2);
  margin-right: var(--mb-2);
}
.grid {
  display: grid;
  gap: 1.5rem;
}
.header {
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: var(--z-fixed);
  background-color: var(--body-color);
}
.section-title,
.section-subtitle {
  text-align: center;
}
.section-title,
.section-subtitle {
  text-align: center;
}

.section-title {
  font-size: var(--h1-font-size);
  color: var(--title-color);
  margin-bottom: var(--mb-3);
}

.section-subtitle {
  display: block;
  color: var(--first-color);
  font-weight: var(--font-medium);
  margin-bottom: var(--mb-1);
}

@media screen and (min-width: 576px) {
  .home_container {
    grid-template-columns: repeat(2, 1fr);
    align-items: center;
  }
}

@media screen and (min-width: 768px) {
  body {
    margin: 0;
  }
  .section {
    padding-top: 8rem;
  }
  .nav {
    height: calc(var(--header-height) + 1.5rem);
  }
  .nav_list {
    display: flex;
  }
  .nav_item {
    margin-left: var(--mb-5);
    margin-bottom: 0;
  }
  .nav_toggle {
    display: none;
  }

  .home_container {
    height: 100vh;
    justify-items: center;
  }
}

@media screen and (min-width: 960px) {
  .container {
    margin-left: auto;
    margin-right: auto;
  }
  .home_img {
    width: 500px;
  }
}
</style>
