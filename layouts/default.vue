<template>
  <div>
    <div
      class="header d-flex justify-content-between align-items-center container"
    >
      <div class="sidebarToggle">
        <el-button
          type="info"
          size="small"
          plain
          icon="el-icon-s-unfold"
          class="mirllex-btn"
        >
        </el-button>
      </div>
      <div>
        <el-button
          type="info"
          size="small"
          plain
          icon="el-icon-circle-plus-outline"
          class="mirllex-btn"
        >
          Разместить объявление
        </el-button>
        <nuxt-link to="/account/login">
          <el-button type="info" size="small" plain class="mirllex-btn">
            Войти
          </el-button>
        </nuxt-link>
      </div>
    </div>

    <div class="sidebar">
      <div class="d-flex flex-column p-3 text-white ">
        <ul class="nav nav-pills flex-column mb-md-0 me-md-auto">
          <li class="nav-item pb-0" style="word-wrap: anywhere">
            <nuxt-link
              to="/"
              class="nav-link text-white d-flex align-items-center"
            >
              <i class="bi bi-building mr-8"></i>
              <span class="logo">RAKHIMOFF</span>
            </nuxt-link>
          </li>
        </ul>
        <!-- <nuxt-link
          to="/"
          class="d-flex  mb-md-0 me-md-auto text-white justify-content-center text-decoration-none"
        >
          <span style="font-size: 20px; font-weight: normal;"
            >Realty Mirllex</span
          >
        </nuxt-link> -->
        <el-divider class="my-18"></el-divider>
        <ul class="nav nav-pills flex-column mb-auto">
          <li class="nav-item" style="word-wrap: anywhere">
            <nuxt-link to="/buy" class="nav-link text-white">
              <i class="bi bi-bag-plus mr-5"></i>
              Купить
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/rent" class="nav-link text-white">
              <i class="bi bi-clipboard-data mr-5"></i>
              Снять
            </nuxt-link>
          </li>
          <li>
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
  </div>
</template>
<script>
import { SlideYDownTransition } from "vue2-transitions";
export default {
  components: {
    SlideYDownTransition
  },
  data() {
    return {};
  },
  methods: {}
};
</script>

<style>
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
.logo {
  font-size: 18px;
  font-family: Baskerville Old Face;
  letter-spacing: 3px;
}

.sidebar {
  word-wrap: break-word;
  /* background: #264c84; */
  background-color: #212529 !important;
  /* background: #fff; */
  height: 100vh;
  width: 230px;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 2;
  background-size: cover;
  background-position: 50%;
  display: block;
  box-shadow: 0 2px 22px 0 rgb(0 0 0 / 10%), 0 4px 20px 0 rgb(0 0 0 / 15%);
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
    display: none;
  }
}
</style>
