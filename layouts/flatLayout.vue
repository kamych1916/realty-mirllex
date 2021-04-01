<template>
  <div class="container">
    <header
      class="header d-flex justify-content-between align-items-center container py-20"
    >
      <nuxt-link to="/" class="header-btn">
        <i class="bi bi-building mr-8"></i>
        <span>flatmy</span>
      </nuxt-link>
      <div class="events">
        <nuxt-link to="/account/add_post" class="header-btn mx-10">
          <i class="bi bi-plus-circle mr-10"></i>
          Разместить объявление
        </nuxt-link>
        <nuxt-link to="/account/login" class="header-btn">
          Войти
        </nuxt-link>
      </div>
      <div class="sidebar ">
        <i class="bi bi bi-list-ul mr-8"></i>
        Меню
      </div>
    </header>
    <Nuxt />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.header {
  .header-btn {
    padding: 10px;
    color: black;
    text-decoration: none;
    border-radius: 10px;
    transition: 0.2s;
    &:hover {
      color: #fff;
      background-color: #3a8ee6;
    }
  }
  .sidebar {
    display: none;
  }
  @media screen and (max-width: 1024px) {
    .events {
      display: none;
    }
    .sidebar {
      display: block;
    }
  }
}
</style>
