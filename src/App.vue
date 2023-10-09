<template>
  <div>
    <nav class="navbar">
      <ul class="menu">
        <li :class="{ active: activeTab === 'home' }">
          <a @click="changeTab('home')">Главная</a>
        </li>
        <li :class="{ active: activeTab === 'about' }">
          <a @click="changeTab('about')">О нас</a>
        </li>
        <li :class="{ active: activeTab === 'films' }">
          <a @click="changeTab('films')">Новинки</a>
        </li>
        <li :class="{ active: activeTab === 'table' }">
          <a @click="changeTab('table')">Расписание</a>
        </li>
        <li :class="{ active: activeTab === 'contact' }">
          <a @click="changeTab('contact')">Контактная информация</a>
        </li>
      </ul>
      <transition name="fade" mode="out-in">
        <i class="hamburgerButton" v-if="!show" @click="show = !show" key="menu">меню</i>
        <i class="closeHamburger" v-else @click="show = !show" key="clear">✖</i>
      </transition>
      <transition name="fade">
        <ul v-if="show" class="burgerUl">
          <li :class="{ active: activeTab === 'home' }">
            <a @click="changeTab('home')">Главная</a>
          </li>
          <li :class="{ active: activeTab === 'about' }">
            <a @click="changeTab('about')">О нас</a>
          </li>
          <li :class="{ active: activeTab === 'films' }">
            <a @click="changeTab('films')">Новинки</a>
          </li>
          <li :class="{ active: activeTab === 'table' }">
            <a @click="changeTab('table')">Расписание</a>
          </li>
          <li :class="{ active: activeTab === 'contact' }">
            <a @click="changeTab('contact')">Контактная информация</a>
          </li>
        </ul>
      </transition>
    </nav>

    <div class="content">
      <div v-show="activeTab === 'home'">
        <TitleScreen />
      </div>
      <div v-show="activeTab === 'about'">
        <AboutScreen />
      </div>
      <div v-show="activeTab === 'films'">
        <FilmsScreen />
      </div>
      <div v-show="activeTab === 'table'">
        <TableScreen />
      </div>
      <div v-show="activeTab === 'contact'">
        <ContactsScreen />
      </div>
    </div>
  </div>
</template>



<script>
import TitleScreen from "./components/TitleScreen.vue";
import AboutScreen from "./components/AboutScreen.vue";
import FilmsScreen from "./components/FilmsScreen.vue";
import TableScreen from "./components/TableScreen.vue";
import ContactsScreen from "./components/ContactsScreen.vue";


export default {
  data() {
    return {
      activeTab: 'home',
      backgroundImages: {
        home: require('@/assets/BG1.jpg'),
        about: require('@/assets/BG2.jpg'),
        films: require('@/assets/BG3.jpg'),
        table: require('@/assets/BG4.jpg'),
        contact: require('@/assets/BG5.jpg'),
      },
      show: false
    };
  },
  components: {
    TitleScreen,
    AboutScreen,
    FilmsScreen,
    TableScreen,
    ContactsScreen
  },
  methods: {
    changeTab(tab) {
      this.activeTab = tab;
      document.body.style.backgroundImage = `url(${this.backgroundImages[tab]})`;
    }
  }
};
</script>

<style>
* {
  font-family: 'Open Sans', sans-serif;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  background: url(@/assets/BG1.jpg) center;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 50px;
  padding: 5px 20px;
  background-color: rgb(27, 27, 27);
  display: flex;
  align-items: center;
  z-index: 2;
}

.menu {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.navbar li {
  padding: 8px 25px;
}

.navbar li a {
  color: rgb(255, 255, 255);
  text-decoration: none;
  font-size: 1em;
  cursor: pointer;
}

.navbar li.active a {
  font-weight: bold;
  font-size: 1.1em;
  color: #d50000;
  cursor: pointer;
}

.hamburgerButton,
.closeHamburger {
  color: rgb(255, 255, 255);
  text-decoration: none;
  font-size: 1em;
  cursor: pointer;
}

.burgerUl {
  align-self: flex-start;
  background: #2e2e2e;
  margin: 0;
  padding: 0;
  position: absolute;
  top: 60px;
  left: 0;
  width: 100%;
}

.burgerUl li {
  align-items: center;
  cursor: pointer;
  display: flex;
  font-size: 1.2em;
  justify-content: center;
  list-style-type: none;
  transition: all .3s ease;
}



.fade-enter-active,
.fade-leave-active {
  transition: opacity .3s ease;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}

@media all and (min-width: 1200px) {

  .hamburgerButton,
  .closeHamburger {
    display: none;
  }
}

@media all and (min-width: 800px) and (max-width: 1200px) {

  .hamburgerButton,
  .closeHamburger {
    display: none;
  }
}

@media all and (min-width: 550px) and (max-width: 800px) {
  .menu {
    display: none;
  }
}

@media all and (max-width: 550px) {
  .menu {
    display: none;
  }
}
</style>
