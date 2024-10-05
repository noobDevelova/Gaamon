<template>
  <aside class="sidebar">
    <div class="sidebar-wrapper">
      <div class="button-link-wrap">
        <slot name="my-profile"></slot>
      </div>
      <div class="button-link-wrap">
        <slot name="my-group"></slot>
      </div>
      <div class="button-link-wrap">
        <slot name="gaamon-pay"></slot>
      </div>
      <div class="button-link-wrap">
        <slot name="purchase-history"></slot>
      </div>
      <div class="button-link-wrap">
        <slot name="payment-method"></slot>
      </div>
      <div class="button-link-wrap">
        <slot name="saved"></slot>
      </div>
      <div class="button-link-wrap">
        <slot name="setting"></slot>
      </div>
    </div>
  </aside>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables";

.sidebar {
  .sidebar-wrapper {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
}
</style>
