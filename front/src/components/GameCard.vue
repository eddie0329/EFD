<template>
  <div
    v-if="loadState === 'LOADING'"
    class="arena-loading-card-container"
  ></div>
  <div v-else class="arena-card-container" @click="onClickCard" data-test-game-card>
    <div class="main-title" data-test-main-title>{{ mainTitle }}</div>
    <div class="sub-title" data-test-sub-title>{{ subTitle }}</div>
  </div>
</template>

<script>
export default {
  props: {
    mainTitle: {
      type: String,
      default: ""
    },
    subTitle: {
      type: String,
      default: ""
    },
    loadState: {
      type: String,
      default: "LOADING"
    },
    isDarkMode: {
      type: Boolean,
      default: false,
    }
  },
  methods: {
    onClickCard() {
      this.$emit("click");
      console.log(this.isDarkMode);
    }
  }
};
</script>

<style scoped>
.arena-loading-card-container {
  background: #000000;
  opacity: 0.1;
  width: 305px;
  height: 421px;
  border-radius: 8px;
}
.arena-card-container {
  background: #181919;
  width: 305px;
  height: 421px;
  border-radius: 8px;
}
.sub-title {
  color: #ffffff;
  font-size: 14px;
}
.main-title {
  top: 305px;
  left: 14px;
  font-size: 28px;
  letter-spacing: 0.54px;
  color: #eb1302;
}
</style>