<template>
  <div class="header">
    <div class="container">
      <div class="header__wrapper">
        <ul class="header__list">
          <a href="#"><li class="header__item">Каталог</li></a>
          <a href="#"><li class="header__item">Доставка</li></a>
          <a href="#"><li class="header__item">Оплата</li></a>
          <a href="#"><li class="header__item">Контакты</li></a>
          <a href="#"><li class="header__item">О компании</li></a>
        </ul>
        <div class="header__search">
          <MyInput type="text" :placeholder="'Поиск по названию картины'" />
          <MyButton class="header__btn">Найти</MyButton>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import MyButton from "@/components/UI/MyButton.vue";
import MyInput from "@/components/UI/MyInput.vue";
export default {
  components: {
    MyButton,
    MyInput,
  },
};
</script>
<style lang="scss">
.container {
  width: 1150px;
  margin: 0 auto;
}
.header {
  margin-top: 25px;
  &__wrapper {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__list {
    display: flex;
    justify-content: space-between;
  }
  &__item {
    font-weight: 400;
    font-size: 14px;
    line-height: 150%;
    margin-right: 48px;
    color: #343030;
  }
  &__btn {
    color: #ffffff;
    font-weight: 700;
    font-size: 14px;
    line-height: 150%;
  }
}
.header__list:last-child {
  margin-right: 0;
}
</style>
