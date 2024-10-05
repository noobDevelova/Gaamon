<template>
  <div class="backdrop" @click.self="handleClose">
    <div class="modal-plate">
      <button type="button" class="close-modal-btn">
        <span class="material-symbols-outlined" @click.self="handleClose">
          close
        </span>
      </button>
      <slot></slot>
      <div class="button-wrapper">
        <slot name="button-method"></slot>
      </div>
      <div class="input-wrapper">
        <slot name="input"> </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleClose() {
      this.$emit("close");
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.backdrop {
  position: fixed;
  top: 0;
  background-color: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  z-index: 200;
  display: flex;
  align-items: center;
  justify-content: center;
  animation: fadeIn 0.5s;

  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  .modal-plate {
    position: relative;
    width: 520px;
    height: 700px;
    border: 4px solid black;
    border-radius: 0px;
    box-shadow: 4px 4px 0px #000000;
    background: $primary20;
    margin-inline: auto;
    padding: 25px;

    .close-modal-btn {
      width: 30px;
      height: 30px;
      background-color: $kuningSummer;
      border-radius: 0px;
      border: 2px solid black;
      box-shadow: 2px 2px 0px #000000;
      padding: 0;
      position: absolute;
      right: 25px;
    }
  }
}
</style>
