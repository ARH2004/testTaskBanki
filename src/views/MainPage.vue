<template>
  <div class="mainPage">
    <vHeader></vHeader>
    <vFooter></vFooter>
  </div>
</template>

<script>
import vHeader from "@/components/vHeader.vue";
import vFooter from "@/components/vFooter.vue";
export default {
  name: "HomeView",
  components: {
    vHeader,
    vFooter,
  },
};
</script>
