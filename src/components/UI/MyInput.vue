<template>
  <input :placeholder="placeholder" class="input" />
</template>
<script>
export default {
  props: {
    placeholder: {
      type: String,
    },
  },
};
</script>
<style lang="scss" scoped>
.input {
  height: 48px;
  width: 295px;
  border: 1px solid #e1e1e1;
  padding: 13px 0px 14px 16px;
}
::placeholder {
  font-size: 14px;
  line-height: 150%;
  display: flex;
  align-items: center;
  color: #9f9f9f;
}
</style>
