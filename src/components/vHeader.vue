<template>
  <div class="header">
    <div class="container">
      <div class="header__wrapper">
        <div class="header__mob">
          <button class="header__toggle" @click="toggleMenu">
            <span></span>
            <span></span>
            <span></span>
          </button>
        </div>
        <ul class="header__list" :class="{ showList: isOpen === true }">
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
      isOpen: false,
    };
  },
  methods: {
    updateSearchQuery(event) {
      this.searchQuery = event.target.value;
      this.$emit("input", this.searchQuery);
    },
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>
<style lang="scss">
.container {
  width: 1150px;
  margin: 0 auto;
  padding: 0px 20px;
}
.header {
  margin-top: 25px;
  position: relative;
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
.header__toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 25px;
  height: 20px;
  cursor: pointer;
}
.header__toggle span {
  display: block;
  width: 100%;
  height: 3px;
  background-color: #333;
  transition: transform 0.3s ease-in-out, opacity 0.3s ease-in-out;
}
.header__toggle:hover span {
  transform: translateY(-2px);
}
@media (max-width: 1300px) {
  .header__toggle {
    display: flex;
    margin-left: 100px;
    position: relative;
  }
  .header__list {
    display: none;
  }
  .header__list--open {
    display: flex;
  }
  .header__item {
    margin-bottom: 10px;
  }
}
.showList {
  display: block;
  position: absolute;
  top: 100%;
  left: 0%;
  background: grey;
  padding: 30px;
}
</style>
