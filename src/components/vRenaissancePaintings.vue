<template>
  <div class="renaissancePaintings">
    <hr class="renaissancePaintings__line" />
    <div class="container">
      <h1 class="renaissancePaintings__title">Картины эпохи Возрождения</h1>
      <div class="renaissancePaintings__cards">
        <div v-for="painting in filteredPaintings" :key="painting.id">
          <vCard
            :image="painting.image"
            :namePainting="painting.namePainting"
            :nameAuthor="painting.nameAuthor"
            :price="painting.price"
            :alternativePrice="painting.alternativePrice"
            :showPrice="painting.showPrice"
            :noPrice="noPrice"
            :idx="painting.idx"
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
      noPrice: "Продана на аукционе",
    };
  },
  props: ["paintings", "searchQuery"],
  computed: {
    filteredPaintings() {
      if (!this.paintings) {
        return [];
      }
      if (!this.searchQuery) {
        return this.paintings;
      }
      const searchLower = this.searchQuery.toLowerCase();
      return this.paintings.filter((painting) => {
        return painting.namePainting.toLowerCase().includes(searchLower);
      });
    },
  },
};
</script>
<style lang="scss">
.container {
  width: 1230px;
  margin: 0 auto;
}
.renaissancePaintings {
  width: 100vw;
  &__line {
    margin: 25px 0px 45px 0px;
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
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    gap: 32px;
    margin-bottom: 50px;
  }
}
@media (max-width: 1300px) {
  .renaissancePaintings {
    &__cards {
      grid-template-columns: 1fr 1fr 1fr;
    }
  }
}
@media (max-width: 768px) {
  .renaissancePaintings {
    &__cards {
      grid-template-columns: 1fr 1fr;
    }
  }
}
@media (max-width: 500px) {
  .renaissancePaintings {
    &__cards {
      grid-template-columns: 1fr;
      position: relative;
      left: 40%;
    }
  }
}
</style>
