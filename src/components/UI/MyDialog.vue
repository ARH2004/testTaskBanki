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
        <div class="wrapper">
          <div
            class="wrapper__carousel"
            :style="{ 'margin-left': '-' + 100 * currentSlideIndex + '%' }"
          >
            <div v-for="item in dataSelectionsSwiper" :key="item.id">
              <img :src="require(`@/assets/${item.image}`)" />
            </div>
          </div>
          <div class="dialog__box-btn">
            <button class="dialog__btn" @click="prevSlide">Назад</button>
            <button class="dialog__btn" @click="nextSlide">Вперед</button>
          </div>
        </div>
      </div>
      <button @click="$emit('close')" class="dialog__closeBtn">Скрыть</button>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dataSelectionsSwiper: [
        {
          id: Date.now(),
          image: "images/imgOne.png",
        },
        {
          id: Date.now(),
          image: "images/imgThree.png",
        },
        {
          id: Date.now(),
          image: "images/imgTwo.png",
        },
        {
          id: Date.now(),
          image: "images/imgFour.png",
        },
      ],
      currentSlideIndex: 0,
    };
  },
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
  methods: {
    prevSlide() {
      if (this.currentSlideIndex > 0) {
        this.currentSlideIndex--;
      }
    },
    nextSlide() {
      if (this.currentSlideIndex >= this.dataSelectionsSwiper.length - 1) {
        this.currentSlideIndex = 0;
      } else {
        this.currentSlideIndex++;
      }
    },
  },
};
</script>
<style lang="scss" scoped>
.wrapper {
  max-width: 280px;
  overflow: hidden;
  margin: 0 auto;
  &__carousel {
    display: flex;
    transition: all ease 0.5s;
  }
}
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
  &__box-btn {
    margin-top: 10px;
    display: flex;
    justify-content: space-between;
  }
  &__btn {
    max-width: 80px;
    border-radius: 20px;
    color: #ffffff;
    font-weight: 700;
    font-size: 14px;
    line-height: 150%;
    height: 48px;
    min-width: 80px;
    background: #403432;
  }
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
  &__gallery {
    margin-top: 40px;
  }
  &__gallery-title {
    text-align: center;
    font-size: 25px;
    margin-bottom: 20px;
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
    margin: 30% 0 0 80%;
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
