<template>
  <div class="mainPage">
    <div>
      <vHeader v-model="searchQuery"></vHeader>
      <vRenaissancePaintings
        :paintings="paintings"
        :searchQuery="searchQuery"
      ></vRenaissancePaintings>
    </div>
    <vFooter></vFooter>
  </div>
</template>

<script>
import vHeader from "@/components/vHeader.vue";
import vFooter from "@/components/vFooter.vue";
import vRenaissancePaintings from "@/components/vRenaissancePaintings.vue";
export default {
  name: "HomeView",
  components: {
    vHeader,
    vFooter,
    vRenaissancePaintings,
  },
  data() {
    return {
      paintings: [
        {
          id: Date.now(),
          image: "images/imgOne.png",
          namePainting: "«Рождение Венеры»",
          nameAuthor: "Сандро Боттичелли",
          alternativePrice: "2 000 000 $",
          price: "1 000 000 $",
          showPrice: true,
        },
        {
          id: Date.now(),
          image: "images/imgTwo.png",
          namePainting: "«Тайная вечеря»",
          nameAuthor: "Леонардо да Винчи",
          price: "3 000 000 $",
          showPrice: true,
        },
        {
          id: Date.now(),
          image: "images/imgThree.png",
          namePainting: "«Сотворение Адама»",
          nameAuthor: "Микеланджело",
          alternativePrice: "6 000 000 $",
          price: "5 000 000 $",
          showPrice: true,
        },
        {
          id: Date.now(),
          image: "images/imgFour.png",
          namePainting: "«Урок анатомии»",
          nameAuthor: "Рембрандт",
          showPrice: false,
        },
      ],
      searchQuery: "",
    };
  },
  methods: {
    updateSearchText(searchText) {
      this.searchText = searchText;
    },
  },
};
</script>
<style lang="scss" scoped>
.mainPage {
  height: 100vh;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
</style>
