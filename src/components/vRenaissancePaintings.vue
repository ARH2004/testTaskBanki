<template>
  <div class="renaissancePaintings">
    <hr class="renaissancePaintings__line" />

    <div class="container">
      <h1 class="renaissancePaintings__title">Картины эпохи Возрождения</h1>
      <div
        class="renaissancePaintings__cards"
        v-for="item in dt"
        :key="item.id"
      >
        <vCard
          :image="item.imageOne"
          :name="item.nameOne"
          :price="'1 000 000$'"
        ></vCard>
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
          imageOne: "../assets/images/imgOne.png",
          nameOne: "«Рождение Венеры» Сандро Боттичелли",
        },
        {
          id: Date.now(),
          imageOne: "@/assets/images/imgTwo.png",
          nameOne: "«Тайная вечеря»  Леонардо да Винчи",
        },
        {
          id: Date.now(),
          imageOne: "@/assets/images/imgThree.png",
          nameOne: "«Сотворение Адама» Микеланджело",
        },
        {
          id: Date.now(),
          imageOne: "@/assets/images/imgFour.png",
          nameOne: "«Урок анатомии»  Рембрандт",
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
