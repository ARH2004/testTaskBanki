<template>
  <div class="card">
    <img
      :src="require('../assets/' + image)"
      alt="image"
      class="card__img"
      :class="{ altColorImg: showPrice === false }"
    />
    <div class="card__info-card">
      <h2 class="card__painting" :class="{ altColor: showPrice === false }">
        {{ namePainting }}
      </h2>
      <h2 class="card__author" :class="{ altColor: showPrice === false }">
        {{ nameAuthor }}
      </h2>
      <div class="card__priceAndBtn" v-if="showPrice">
        <div class="card__priceBlock">
          <p class="card__alternativePrice">{{ alternativePrice }}</p>
          <p class="card__price">{{ price }}</p>
        </div>
        <MyButton class="card__btn">Купить</MyButton>
      </div>
      <p class="card__notAvailable" v-else>Продана на аукционе</p>
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
    nameAuthor: {
      type: String,
      required: true,
    },
    namePainting: {
      type: String,
      required: true,
    },
    alternativePrice: {
      type: String,
    },
    price: {
      type: String,
    },
    showPrice: {
      type: Boolean,
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
  &__painting {
    max-width: 220px;
    font-weight: 400;
    font-size: 18px;
    line-height: 150%;
    color: #343030;
  }
  &__author {
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
  &__alternativePrice {
    font-weight: 300;
    font-size: 14px;
    line-height: 150%;
    text-decoration-line: line-through;
    color: #a0a0a0;
  }
  &__price {
    font-weight: 700;
    font-size: 16px;
    line-height: 150%;
    color: #343030;
  }
  &__btn {
    color: #f4f6f9;
    font-weight: 700;
    font-size: 14px;
    line-height: 150%;
  }
  &__notAvailable {
    margin-top: 35px;
    font-weight: 700;
    font-size: 16px;
    line-height: 150%;
    color: #a0a0a0;
  }
}
.altColorImg {
  opacity: 0.5;
}
.altColor {
  color: #a0a0a0;
}
</style>
