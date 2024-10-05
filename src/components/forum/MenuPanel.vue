<template>
  <aside class="menu-panel">
    <div class="section top">
      <h3 class="title">Menu</h3>
      <ul class="menu-wrap">
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> forum </span>
          </div>
          Forum
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <img src="@/assets/img/topup.svg" alt="topup_icon" />
          </div>
          Top Up
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <img src="@/assets/img/turnament.svg" alt="topup_icon" />
          </div>
          Tournament
        </li>
      </ul>
    </div>
    <div class="section bottom">
      <ul class="menu-wrap">
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> person </span>
          </div>
          My Profile
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> bookmark </span>
          </div>
          Saved
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <img src="@/assets/img/purchase_history.svg" alt="topup_icon" />
          </div>
          Purchase History
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> group </span>
          </div>
          My Group
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> credit_card </span>
          </div>
          Payment Method
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> language </span>
          </div>
          Language
        </li>
        <li class="menu-item">
          <div class="icon-box">
            <span class="material-symbols-outlined"> logout </span>
          </div>
          Log Out
        </li>
      </ul>
    </div>
  </aside>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables.scss";
.menu-panel {
  position: fixed;
  right: 0;
  width: 299px;
  height: 100vh;
  background-color: $oyenForum;
  border-left: 2px solid black;
  float: right;

  .section {
    padding: 20px;
    padding-inline: 46px;

    .menu-wrap {
      display: flex;
      padding: 0;
      flex-direction: column;
      gap: 25px;
      .menu-item {
        display: flex;
        flex-direction: row;
        gap: 1rem;
        align-items: center;
        list-style: none;
        width: 100%;
        padding: 10.5px 15px;
        border: 2px solid transparent;
        @include font-weight(semibold);
        font-size: 14px;

        &:hover {
          border: 2px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 5px;
        }
        .icon-box {
          width: 34px;
          height: 34px;
          padding: 2.5px;
          background-color: $kuningEternal;
          border: 2px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 2px;

          span {
            margin: 0;
            padding: 0;
          }
        }
      }
    }
  }
  .top {
    border-bottom: 2px solid black;

    .title {
      text-align: center;
      @include font-weight(bold);
      margin-bottom: 20px;
    }
  }
  .bottom {
    background-color: $kuningEternal;
    height: 100%;
  }
}
</style>
