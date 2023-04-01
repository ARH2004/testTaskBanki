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
          <input
            type="text"
            class="header__input"
            :placeholder="'Поиск по названию картины'"
            :value="searchQuery"
            @input="updateSearchQuery"
          />
          <MyButton class="header__btn">Найти</MyButton>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
  components: {
    MyButton,
  },
  props: ["value"],
  data() {
    return {
      searchQuery: this.value,
    };
  },
  methods: {
    updateSearchQuery(event) {
      this.searchQuery = event.target.value;
      this.$emit("input", this.searchQuery);
    },
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
  &__input {
    height: 48px;
    width: 295px;
    border: 1px solid #e1e1e1;
    padding: 13px 0px 14px 16px;
  }
}
.header__input:focus {
  border: 1px solid #b5b5b5;
}
::placeholder {
  font-size: 14px;
  line-height: 150%;
  display: flex;
  align-items: center;
  color: #9f9f9f;
}
.header__list:last-child {
  margin-right: 0;
}
</style>
