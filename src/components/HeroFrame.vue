<template>
  <div class="hero-frame">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";
.hero-frame {
  width: 100%;
  height: auto;
  padding-top: 10px;
  padding-inline: 11px;
  background-color: $kuningSummer;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;
}
</style>
