<template>
  <button
    class="btn"
    :class="{ 'btn-processing': processing, 'btn-added': added }"
    @click="handleClick"
  >
    <span v-if="!processing">
      <img
        v-if="added"
        class="btn__checkMark"
        src="@/assets/images/icons/checkMark.svg"
        alt="checkMark"
      />
      {{ added ? "В корзине" : "Купить" }}
    </span>
    <span v-else>
      <span class="spinner"></span>
      <span v-if="processing" class="btn__processed">Oбрабатывается</span>
    </span>
  </button>
</template>
<script>
export default {
  props: {
    idx: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      processing: false,
      added: false,
    };
  },
  mounted() {
    const state = JSON.parse(localStorage.getItem(`button-state-${this.idx}`));
    if (state) {
      this.processing = state.processing;
      this.added = state.added;
    }
  },
  methods: {
    handleClick() {
      if (!this.added) {
        this.processing = true;
        setTimeout(() => {
          this.processing = false;
          this.added = true;
          this.saveState();
        }, 2000);
      }
    },
    saveState() {
      const state = {
        processing: this.processing,
        added: this.added,
      };
      localStorage.setItem(`button-state-${this.idx}`, JSON.stringify(state));
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  height: 48px;
  min-width: 120px;
  background: #403432;
  &__checkMark {
    padding-top: 3px;
  }
  &__processed {
    margin: 0px 4px;
    font-size: 12px;
  }
}
.btn:hover {
  background: #776763;
  color: #f4f6f9;
}
.spinner {
  margin: 0px 5px 0px 5px;
  display: inline-block;
  width: 10px;
  height: 10px;
  border: 2px solid #fff;
  border-top-color: #403432;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
