<template>
  <div class="chat-frame">
    <img src="../../assets/img/chitchat_icon.svg" alt="chitchat_logo" />
    <div class="content-wrapper">
      <div class="search-wrapper">
        <slot name="search"></slot>
      </div>
      <div class="chat-wrapper">
        <slot name="chat"> </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.chat-frame {
  width: 380px;
  height: 355px;
  background-color: $merahCrimson;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;
  padding: 10px;
}
</style>
