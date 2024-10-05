<template>
  <div class="setting-box">
    <div class="box-header">
      <h3>Setting</h3>
      <router-link to="/" class="close-button">
        <span class="material-symbols-outlined"> close </span>
      </router-link>
    </div>
    <div class="box-body"></div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.setting-box {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 700px;
  background-color: $kuningEternal;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;

  .box-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    border-bottom: 2px solid black;
    height: 80px;
    padding: 22px 20px 20px 25px;

    h3 {
      @include font-weight(bold);
      font-size: 18px;
      line-height: 22px;
      margin-top: 6px;
    }

    .close-button {
      width: 30px;
      height: 30px;
      border: 1px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      padding: 2px;
      span {
        margin: 0;
        color: black;
      }
    }
  }

  .box-body {
    display: flex;
    flex-direction: column;
    gap: 30px;
    padding: 22px 20px 0px 25px;
  }
}
</style>
