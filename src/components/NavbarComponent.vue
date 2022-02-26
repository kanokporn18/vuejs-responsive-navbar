<template>
  <div>
    <header class="header scroll-header" id="header">
      <nav class="nav container">
        <a class="nav_logo" href="#"><router-link to="/">Demo</router-link></a>
        <div class="nav_menu" id="nav-menu">
          <ul class="nav_list">
            <li class="nav_item">
              <router-link class="nav_link active-link" to="/"
                >Home</router-link
              >
            </li>
            <li class="nav_item">
              <router-link class="nav_link" to="/about">About</router-link>
            </li>
            <li class="nav_item">
              <router-link class="nav_link" to="/">Services</router-link>
            </li>
            <li class="nav_item">
              <router-link class="nav_link" to="/">Contact</router-link>
            </li>
          </ul>
        </div>
        <div class="nav_toggle" id="nav-toggle">
          <i class="bx bx-menu" @click="openMenu"></i>
        </div>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  name: 'NavbarComponent',
  methods: {
    openMenu() {
      const showMenu = (toggleId, navId) => {
        const toggle = document.getElementById(toggleId),
          nav = document.getElementById(navId);

        if (toggle && nav) {
          nav.classList.toggle('show-menu');
        }
      };
      showMenu('nav-toggle', 'nav-menu');

      const sections = document.querySelectorAll('section[id]');
      function scrollActive() {
        const scrollY = window.pageYOffset;
        sections.forEach((current) => {
          const sectionHeight = current.offsetHeight;
          const sectionTop = current.offsetTop - 50;
          const sectionId = current.getAttribute('id');

          if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
            document
              .querySelector('.nav_menu a[href*=' + sectionId + ']')
              .classList.add('active-link');
          } else {
            document
              .querySelector('.nav_menu a[href*=' + sectionId + ']')
              .classList.remove('active-link');
          }
        });
      }
      window.addEventListener('scroll', scrollActive);
    },
  },
};
</script>

<style scoped>
.nav {
  max-width: 1024px;
  height: var(--header-height);
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.nav_link,
.nav_logo a,
.nav_toggle {
  color: var(--text-color);
  font-weight: var(--font-medium);
}
.nav_logo:hover a {
  color: var(--first-color);
}

.nav_link:hover {
  color: var(--first-color);
}

@media screen and (max-width: 768px) {
  .nav_menu {
    background: var(--body-color);
    position: fixed;
    /* top: var(--header-height); */
    top: -100%;
    left: 0;
    width: 100%;
    padding: 1.5rem 0 1rem;
    text-align: center;
    transition: 0.4s;
    box-shadow: 0 4px 4px rgba(0, 0, 0, 0.1);
    border-radius: 0 0 1rem 1rem;
    z-index: var(--z-fixed);
  }
  .nav_item {
    margin-bottom: var(--mb-2);
  }

  .nav_logo:hover a {
    color: var(--first-color);
  }
  .nav_link {
    transition: 0.3s;
  }
  .nav_link:hover {
    color: var(--first-color);
  }
  .nav_toggle {
    font-size: 1.3rem;
    cursor: pointer;
  }
  .show-menu {
    top: var(--header-height);
  }
  .active-link {
    color: var(--first-color);
  }
  .scroll-header {
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
}
</style>
