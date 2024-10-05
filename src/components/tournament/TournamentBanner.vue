<template>
  <div class="banner-frame">
    <div class="img-wrap">
      <slot name="banner-img"></slot>
    </div>
    <div class="banner-title">
      <slot name="banner-title"></slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.banner-frame {
  .img-wrap {
    border: 1px solid black;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 2px;
  }
}
</style>
