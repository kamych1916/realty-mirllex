<template>
  <div class="card-wrap">
    <div class="auth-template">
      <form @submit.prevent="onSubmit()" autocomplete="off">
        <h3>Регистрация</h3>

        <div class="form-group">
          <label>Имя</label>
          <el-input
            required
            v-model="userData.name"
            clearable
            type="text"
            name="name"
          ></el-input>
        </div>

        <div class="form-group">
          <label>Фамилия</label>
          <el-input
            required
            v-model="userData.surname"
            clearable
            type="text"
            name="surname"
          ></el-input>
        </div>

        <div class="form-group">
          <label>Отчество</label>
          <el-input
            required
            v-model="userData.patronymic"
            clearable
            type="text"
            name="patronomic"
          ></el-input>
        </div>

        <div class="form-group">
          <label>Номер телефона</label>
          <el-input
            required
            v-model="userData.tel"
            clearable
            pattern="\+[0-9]{3} \([0-9]{3}\)-[0-9]{2}-[0-9]{2}-[0-9]{2}"
            v-mask="'+992 (###)-##-##-##'"
            placeholder="+992 (000) 00-00-00"
            title="+992 (000)-00-00-00"
            type="text"
          ></el-input>
        </div>

        <div class="form-group">
          <label>E-mail адрес</label>
          <el-input
            required
            v-model="userData.email"
            name="email"
            clearable
            pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$"
            type="email"
          ></el-input>
        </div>

        <div class="form-group">
          <label>Пароль</label>
          <el-input
            required
            v-model="userData.password"
            name="password"
            auto-complete="off"
            show-password
            pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
            title="Не менее восьми символов, содержащих хотя бы одну цифру и символы из верхнего и нижнего регистра"
            type="password"
          ></el-input>
        </div>

        <div class="form-group">
          <label>Подтвердите пароль</label>
          <el-input
            required
            v-model="passwordS"
            name="password"
            auto-complete="off"
            show-password
            pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
            title="Не менее восьми символов, содержащих хотя бы одну цифру и символы из верхнего и нижнего регистра"
            type="password"
          ></el-input>
        </div>

        <button type="submit" class="btn btn-dark btn-lg btn-block mt-3">
          Регистрация
        </button>

        <p class="forgot-password text-right">
          Имеете аккаунт ?
          <router-link to="/account/login">Авторизоваться</router-link>
        </p>
      </form>
    </div>
  </div>
</template>

<script>
import Api from "~/utils/api";
import NTFS from "~/utils/notifications";
export default {
  data() {
    return {
      userData: {
        name: null,
        surname: null,
        patronymic: null,
        tel: null,
        email: null,
        password: null
      },
      passwordS: null
    };
  },
  methods: {
    onSubmit() {
      if (this.userData.password != this.passwordS) {
        this.sendNTFS("Ошибка", "Пароли не совпадают :(", "warning");
      } else {
        Api.getInstance()
          .auth.register(this.userData)
          .then(response => {
            this.sendNTFS("Отлично!", "Регистрация прошла успешно!", "success");
            setTimeout(() => {
              this.$router.push("/account/login");
            }, 1500);
          })
          .catch(error => {
            let status = error.response.status;
            if (status == 500) {
              this.sendNTFS("Ошибка", "Сервер не доступен :(", "error");
            } else if (status == 422) {
              this.sendNTFS(
                "Ошибка",
                "Сервер получил неверные данные :(",
                "error"
              );
            } else if (status == 401) {
              this.sendNTFS(
                "Ошибка",
                "Данный пользователь уже существует!",
                "warning"
              );
            } else if (status == 409) {
              this.sendNTFS(
                "Ошибка",
                "Область введена неправильно!",
                "warning"
              );
            }
          });
      }
    },
    sendNTFS(title, message, type) {
      NTFS.getInstance().NTFS(title, message, type);
    }
  }
};
</script>

<style></style>
