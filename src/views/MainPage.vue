<template>
  <div class="mainPage">
    <div>
      <vHeader></vHeader>
      <vRenaissancePaintings></vRenaissancePaintings>
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
