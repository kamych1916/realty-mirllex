<template>
  <div>
    <div class="card-wrap">
      <h4>Недвижимость в Таджикистане</h4>
    </div>
    <div class="row">
      <div class="col-md-6">
        <div class="card-wrap">
          <img width="100%" src="/images/buy.jpg" class="mb-10" />
          <h6 class="mb-10">Купить квартиру</h6>

          <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item" style="word-wrap: anywhere">
              <nuxt-link to="/buy" class="nav-link text-dark">
                1-комнатные
                <span style="font-size: 0.8rem; color: #ccc"> 1 686</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/rent" class="nav-link text-dark">
                2-комнатные
                <span style="font-size: 0.8rem; color: #ccc"> 2 070</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                3-комнатные
                <span style="font-size: 0.8rem; color: #ccc"> 1 237</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                Квартиры-студии
                <span style="font-size: 0.8rem; color: #ccc"> 27</span>
              </nuxt-link>
            </li>
          </ul>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card-wrap">
          <img width="100%" src="/images/rent.jpg" class="mb-10" />
          <h6 class="mb-10">Снять квартиру</h6>
          <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item" style="word-wrap: anywhere">
              <nuxt-link to="/buy" class="nav-link text-dark">
                1-комнатные
                <span style="font-size: 0.8rem; color: #ccc"> 1 686</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/rent" class="nav-link text-dark">
                2-комнатные
                <span style="font-size: 0.8rem; color: #ccc"> 2 070</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                3-комнатные
                <span style="font-size: 0.8rem; color: #ccc"> 1 237</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                Жилой дом
                <span style="font-size: 0.8rem; color: #ccc"> 59</span>
              </nuxt-link>
            </li>
          </ul>
        </div>
      </div>

      <div class="col-md-6">
        <div class="card-wrap">
          <img width="100%" src="/images/office.jpg" class="mb-10" />
          <h6 class="mb-10">Коммерческая недвижимость</h6>
          <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item" style="word-wrap: anywhere">
              <nuxt-link to="/buy" class="nav-link text-dark">
                Купить склад
                <span style="font-size: 0.8rem; color: #ccc"> 1 686</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/rent" class="nav-link text-dark">
                Купить гараж
                <span style="font-size: 0.8rem; color: #ccc"> 2 070</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                Купить офис
                <span style="font-size: 0.8rem; color: #ccc"> 1 237</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                Арендовать офис
                <span style="font-size: 0.8rem; color: #ccc"> 59</span>
              </nuxt-link>
            </li>
          </ul>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card-wrap">
          <img width="100%" src="/images/home.jpg" class="mb-10" />
          <h6 class="mb-10">Загородная недвижимость</h6>
          <ul class="nav nav-pills flex-column mb-auto">
            <li class="nav-item" style="word-wrap: anywhere">
              <nuxt-link to="/buy" class="nav-link text-dark">
                Купить дом
                <span style="font-size: 0.8rem; color: #ccc"> 1 686</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/rent" class="nav-link text-dark">
                Купить участок
                <span style="font-size: 0.8rem; color: #ccc"> 2 070</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                Купить посёлков
                <span style="font-size: 0.8rem; color: #ccc"> 1 237</span>
              </nuxt-link>
            </li>
            <li>
              <nuxt-link to="/knock" class="nav-link text-dark">
                Снять дом надолго
                <span style="font-size: 0.8rem; color: #ccc"> 59</span>
              </nuxt-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.nav li {
  padding-bottom: 0px;
}
.nav li:hover {
  background: #fdfbfb;
}
</style>
