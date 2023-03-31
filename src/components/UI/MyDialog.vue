<template>
  <div class="dialog" v-show="visible">
    <div class="dialog__content">
      <h2 class="dialog__description">Краткое описание позици</h2>
      <div class="dialog__description-box">
        <h2 class="dialog__name">Наименование: {{ namePaintingDialog }}</h2>
        <h3 class="dialog__author">Автор: {{ nameAuthorDialog }}</h3>
        <h3 class="dialog__price">
          Цена: {{ namePriceDialog ? namePriceDialog : noPriceDialog }}
        </h3>
      </div>
      <div class="dialog__gallery">
        <h4 class="dialog__gallery-title">Галерея</h4>
      </div>
      <button @click="$emit('close')" class="dialog__closeBtn">Close</button>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    visible: {
      type: Boolean,
      required: true,
    },
    namePaintingDialog: {
      type: String,
      required: true,
    },
    nameAuthorDialog: {
      type: String,
      required: true,
    },
    namePriceDialog: {
      type: String,
    },
    noPriceDialog: {
      type: String,
    },
  },
};
</script>
<style lang="scss" scoped>
.dialog {
  position: relative;
  z-index: 10;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.2);
  position: fixed;
  display: flex;
  &__content {
    margin: auto;
    background: white;
    border-radius: 12px;
    min-height: 600px;
    min-width: 800px;
    padding: 20px;
  }
  &__description-box {
    margin-top: 40px;
  }
  &__gallery-title {
    text-align: center;
    font-size: 25px;
  }
  &__description {
    font-size: 25px;
    text-align: center;
  }
  &__author {
    font-size: 20px;
    margin-top: 20px;
  }
  &__name {
    font-size: 20px;
  }
  &__price {
    font-size: 20px;
    margin-top: 20px;
  }
  &__closeBtn {
    margin: 70% 0 0 80%;
    color: #ffffff;
    font-weight: 700;
    font-size: 18px;
    line-height: 150%;
    height: 48px;
    min-width: 120px;
    background: #403432;
  }
}
</style>
