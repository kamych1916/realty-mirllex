<template>
  <div class="main-block" style="postion:relative">
    <div class="backdrop"></div>
    <div class="title-block">
      <div class="row d-flex justify-content-center">
        <div class="col-md-5 title my-30">
          Ищи <br />
          на флэтмай
        </div>
        <div class="col-md-4 my-30">
          <div class="wrap-search">
            <el-select
              v-model="type_offer"
              placeholder="Выберите тип недвижимости"
              class="w-100 p-10 "
            >
              <el-option
                v-for="item in kind_options"
                :key="item.value"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
            <el-select
              v-model="kind_offer"
              placeholder="Выберите вид сделки"
              class="w-100 p-10"
            >
              <el-option
                v-for="item in type_options"
                :key="item.value"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
            <div class="w-100 p-10">
              <el-button type="primary" round class="w-100 py-14"
                >найти</el-button
              >
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="row my-50 d-flex justify-content-center">
      <div class="col-md-12">
        <div class="row">
          <div class="col-md-4 mt-30">
            <div class="wrap-img h-100">
              <span class="title-img ">Новостройки</span>
              <img
                src="/images/flatmy-newBuildings.jpg"
                style="object-fit: cover; "
                width="100%"
                height="100%"
              />
            </div>
          </div>
          <div class="col-md-8 ">
            <div class="row mt-30">
              <div class="col d-flex">
                <div class="wrap-img h-100">
                  <span class="title-img ">Продажа квартир</span>
                  <img
                    src="/images/flatmy-buy.jpg"
                    style="object-fit: cover; "
                    width="100%"
                  />
                </div>
              </div>
              <div class="col d-flex">
                <div class="wrap-img h-100">
                  <span class="title-img ">Аренда квартир</span>
                  <img
                    src="/images/flatmy-rent.jpg"
                    style="object-fit: cover; "
                    width="100%"
                  />
                </div>
              </div>
            </div>
            <div class="row mt-30">
              <div class="col d-flex">
                <div class="wrap-img h-100">
                  <span class="title-img ">Коммерческая</span>
                  <img
                    src="/images/flatmy-office.jpg"
                    style="object-fit: cover; "
                    width="100%"
                  />
                </div>
              </div>
              <div class="col d-flex">
                <div class="wrap-img h-100">
                  <span class="title-img ">Аренда домов</span>
                  <img
                    src="/images/flatmy-home.jpg"
                    style="object-fit: cover; "
                    width="100%"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "flatLayout",
  data() {
    return {
      kind_options: [
        {
          value: "apartment",
          label: "квартира"
        },
        {
          value: "home",
          label: "дом"
        },
        {
          value: "plot",
          label: "участок"
        }
      ],
      type_options: [
        {
          value: "buy",
          label: "купить"
        },
        {
          value: "rent",
          label: "снять"
        },
        {
          value: "daily",
          label: "посуточно"
        }
      ],
      kind_offer: "",
      type_offer: ""
    };
  }
};
</script>

<style lang="scss">
.main-block {
  .backdrop {
    z-index: -1;
    left: 0;
    top: 0;
    position: absolute;
    width: 100%;
    min-height: 700px;
    background-image: linear-gradient(180deg, #e8e8e8, #fff);
  }
  .title-block {
    margin-top: 50px;
    .title {
      color: #27272b;
      font-size: 80px;
      font-weight: 700;
      font-style: normal;
      font-stretch: normal;
      line-height: 0.88;
      letter-spacing: normal;
    }
  }
  .wrap-search {
    background-color: #fff;
    border-radius: 35px;
    box-sizing: border-box;
    padding: 15px;
    .el-input__inner {
      padding: 5px 30px;
      height: auto;
      border: none;
      background-color: #f2f3f7;
      border-radius: 25px;
      color: #409eff;
      &::placeholder {
        color: black;
      }
    }
    .el-input__suffix {
      padding-right: 15px;
    }
  }
  .wrap-img {
    position: relative;
    overflow: hidden;
    cursor: pointer;
    border-radius: 10px;
    .title-img {
      position: absolute;
      top: 0;
      left: 0;
      padding: 15px 20px;
      font-size: 24px;
      font-weight: 700;
      letter-spacing: -0.5px;
      color: #fff;
      z-index: 2;
    }
    img {
      transition: all 0.5s;
    }
    &:hover img {
      transform: scale(1.1);
    }
  }

  @media screen and (max-width: 1024px) {
    .title-block {
      margin-top: 0px;
      .title {
        text-align: center;
        font-size: 50px;
      }
    }

    .wrap-img img {
      height: 180px;
    }
    .wrap-img .title-img {
      padding: 5px 10px;
      font-size: 18px;
    }
  }
}
</style>
