<template>
  <div class="card-wrap">
    <div class="auth-template">
      <form>
        <h3>Восстановление пароля</h3>

        <div class="form-group">
          <label>E-mail адрес</label>
          <el-input
            v-model="userData.email"
            clearable
            type="email"
            pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$"
          ></el-input>
        </div>

        <button type="submit" class="btn btn-dark btn-lg btn-block mt-3">
          Восстановить
        </button>

        <div class="row d-flex justify-content-between px-0 mx-0">
          <p class="forgot-password mt-2 mb-4">
            <router-link to="/account/register">Регистрация </router-link>
          </p>
          <p class="forgot-password mt-2 mb-4">
            <router-link to="/account/login">Авторизация</router-link>
          </p>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        email: null
      }
    };
  }
};
</script>

<style></style>
