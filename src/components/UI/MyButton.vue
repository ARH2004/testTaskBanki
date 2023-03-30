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
  height: 48px;
  width: 120px;
  background: #403432;
}
.btn:hover {
  background: #776763;
  color: #f4f6f9;
}
</style>
