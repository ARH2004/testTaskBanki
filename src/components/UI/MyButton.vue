<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>
<script>
export default {};
</script>
<style lang="scss">
.btn {
  color: #ffffff;
  font-weight: 700;
  font-size: 14px;
  line-height: 150%;
  height: 48px;
  min-width: 120px;
  background: #403432;
}
</style>
