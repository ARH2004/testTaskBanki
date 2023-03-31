<template>
  <div class="renaissancePaintings">
    <hr class="renaissancePaintings__line" />

    <div class="container">
      <h1 class="renaissancePaintings__title">Картины эпохи Возрождения</h1>
      <div class="renaissancePaintings__cards">
        <div v-for="item in dt" :key="item.id">
          <vCard
            :image="item.image"
            :namePainting="item.namePainting"
            :nameAuthor="item.nameAuthor"
            :price="item.price"
          ></vCard>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import vCard from "@/components/vCard.vue";

export default {
  components: { vCard },
  data() {
    return {
      dt: [
        {
          id: Date.now(),
          image: "images/imgOne.png",
          namePainting: "«Рождение Венеры»",
          nameAuthor: "Сандро Боттичелли",
          price: "1 000 000$",
        },
        {
          id: Date.now(),
          image: "images/imgTwo.png",
          namePainting: "«Тайная вечеря»",
          nameAuthor: "Леонардо да Винчи",
          price: "1 000 000$",
        },
        {
          id: Date.now(),
          image: "images/imgThree.png",
          namePainting: "«Сотворение Адама»",
          nameAuthor: "Микеланджело",
          price: "1 000 000$",
        },
        {
          id: Date.now(),
          image: "images/imgFour.png",
          namePainting: "«Урок анатомии»",
          nameAuthor: "Рембрандт",
          price: "1 000 000$",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.container {
  width: 1230px;
  margin: 0 auto;
}
.renaissancePaintings {
  &__line {
    margin: 25px 0px 45px 0px;
    width: 100%;
    height: 1px;
    background-color: #e1e1e1;
  }
  &__title {
    font-weight: 700;
    font-size: 24px;
    line-height: 150%;
    color: #343030;
    margin-bottom: 40px;
  }
  &__cards {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
