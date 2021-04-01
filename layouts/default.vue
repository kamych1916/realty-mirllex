<template>
  <div>
    <div
      class="header d-flex justify-content-between align-items-center container"
    >
      <div>
        <el-button
          type="info"
          size="small"
          plain
          icon="bi bi-list-ul"
          class="mirllex-btn sidebarToggle"
          @click="eventSidebar()"
        >
        </el-button>
      </div>
      <div>
        <nuxt-link to="/account/add_post">
          <el-button
            type="info"
            size="small"
            plain
            icon="el-icon-circle-plus-outline"
            class="mirllex-btn"
          >
            Разместить объявление
          </el-button>
        </nuxt-link>
        <nuxt-link to="/account/login">
          <el-button type="info" size="small" plain class="mirllex-btn">
            Войти
          </el-button>
        </nuxt-link>
      </div>
    </div>

    <div :class="[showSidebar ? 'sidebarActive' : '', 'sidebar']">
      <div class="d-flex flex-column p-16 text-white ">
        <ul class="nav nav-pills flex-column mb-md-0 me-md-auto">
          <div
            @click="eventSidebar()"
            class="close-sidebar nav-link text-white d-flex justify-content-center"
          >
            <li class="nav-item pb-20" style="word-wrap: anywhere">
              <i class="bi bi-x-circle mr-8"></i>
            </li>
          </div>
          <li
            class="nav-item pb-0"
            style="word-wrap: anywhere"
            @click="eventSidebar()"
          >
            <nuxt-link
              to="/"
              class="nav-link text-white d-flex align-items-center"
            >
              <i class="bi bi-building mr-8"></i>
              <span class="logo">RAKHIMOFF</span>
            </nuxt-link>
          </li>
        </ul>

        <el-divider class="my-18"></el-divider>
        <ul class="nav nav-pills flex-column mb-auto">
          <li
            class="nav-item"
            style="word-wrap: anywhere"
            @click="eventSidebar()"
          >
            <nuxt-link to="/buy" class="nav-link text-white">
              <i class="bi bi-bag-plus mr-5"></i>
              Купить
            </nuxt-link>
          </li>
          <li @click="eventSidebar()">
            <nuxt-link to="/rent" class="nav-link text-white">
              <i class="bi bi-clipboard-data mr-5"></i>
              Снять
            </nuxt-link>
          </li>
          <li @click="eventSidebar()">
            <nuxt-link to="/knock" class="nav-link text-white">
              <i class="bi bi-arrow-repeat mr-5"></i>
              Посуточно
            </nuxt-link>
          </li>
        </ul>
      </div>
    </div>
    <div class="content container">
      <slide-y-down-transition :duration="700">
        <Nuxt />
      </slide-y-down-transition>
    </div>
    <div class="backdrop" v-if="showSidebar" @click="eventSidebar()"></div>
  </div>
</template>
<script>
import { SlideYDownTransition } from "vue2-transitions";
export default {
  components: {
    SlideYDownTransition
  },
  data() {
    return {
      showSidebar: false
    };
  },
  methods: {
    eventSidebar() {
      this.showSidebar = !this.showSidebar;
      if (window.screen.width < 1024) {
        if (this.showSidebar) {
          document.body.style.overflow = "hidden";
        } else {
          document.body.style.overflow = "auto";
        }
      }
    }
  }
};
</script>

<style scoped>
html,
body {
  background: #f5f6fa;
}
.content {
  padding-left: 230px;
  min-height: calc(100vh - 80px);
}
.header {
  height: 80px;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1;
  position: relative;
}
.sidebarToggle {
  display: none;
}
.logo {
  font-size: 18px;
  font-family: Baskerville Old Face;
  letter-spacing: 3px;
}

.sidebar {
  transition: all 0.6s;
  word-wrap: break-word;
  background-color: #212529 !important;
  height: 100vh;
  width: 230px;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999999999;
  background-size: cover;
  background-position: 50%;
  display: block;
  box-shadow: 0 2px 22px 0 rgb(0 0 0 / 10%), 0 4px 20px 0 rgb(0 0 0 / 15%);
}
.close-sidebar {
  display: none !important;
}
.backdrop {
  display: none;
  z-index: 1;
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: black;
  opacity: 0.6;
}
.sidebarActive {
  transition: all 0.6s;
  left: 0 !important;
}

.nav li {
  padding-bottom: 20px;
}
.nav a.nuxt-link-exact-active {
  transition: 1s;
  font-weight: normal;
  background: #292d31 !important;
}

@media screen and (max-width: 1024px) {
  .content {
    padding-left: 1rem;
  }
  .sidebar {
    left: -250px;
  }
  .sidebarToggle {
    display: block;
  }
  .close-sidebar {
    display: flex !important;
  }
  .backdrop {
    display: block;
  }
}
</style>
