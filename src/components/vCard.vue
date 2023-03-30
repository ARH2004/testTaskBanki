<template>
  <div class="card">
    <img src="{image}" alt="image" class="card__img" />
    <div class="card__info-card">
      <h2 class="card__name">{{ name }}</h2>
      <div class="card__priceAndBtn">
        <p>{{ price }}</p>
        <MyButton class="card__btn">Купить</MyButton>
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
  props: {
    image: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    price: {
      type: String,
    },
  },
};
</script>
<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  width: 280px;
  height: 330px;
  border: 1px solid #e1e1e1;
  &__info-card {
    padding: 20px 24px 24px 24px;
  }
  &__name {
    max-width: 220px;
    margin-bottom: 22px;
    font-weight: 400;
    font-size: 18px;
    line-height: 150%;
    color: #343030;
  }
  &__priceAndBtn {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &__btn {
    color: #f4f6f9;
    font-weight: 700;
    font-size: 14px;
    line-height: 150%;
  }
}
</style>
