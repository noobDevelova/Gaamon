<template>
  <div class="setting-box">
    <div class="btn-setting hide">
      <span class="material-symbols-outlined saved-icon"> visibility_off </span>
      <span class="btn-text"> Hide Post </span>
    </div>
    <div class="btn-setting report">
      <span class="material-symbols-outlined report-icon"> report </span>
      <span class="btn-text"> Report Post </span>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables.scss";

.setting-box {
  position: absolute;
  right: 20px;
  width: 145px;
  height: 120px;
  background-color: $kuningEternal;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;
  border-radius: 5px;
  padding: 15px 16px;
  display: flex;
  flex-direction: column;
  gap: 10px;

  .btn-setting {
    padding: 6px 0px 6px 5px;
    font-size: 12px;
    border: 2px solid transparent;
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 10px;

    &:hover {
      border: 2px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      border-radius: 5px;
    }
    span {
      padding: 0;
    }
    .btn-text {
      @include font-weight(bold);
      width: 100%;
    }
  }

  .report {
    .report-icon {
      font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 48;
    }
  }
}
</style>
