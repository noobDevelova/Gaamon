<template>
  <aside class="right-bar">
    <div class="header-bar">
      <div class="friends-icon">
        <span class="material-symbols-outlined"> group </span>
      </div>
      <p class="header-title">Friends</p>
      <div class="search-wrapper">
        <span class="material-symbols-outlined"> search </span>
      </div>
    </div>
    <div class="forum-friends-list">
      <div class="friends-wrap">
        <img class="friends-img" src="../../assets/img/profile_ex.svg" alt="" />
        <p class="friends-name">Jamal</p>
      </div>
    </div>
  </aside>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.right-bar {
  position: fixed;
  right: 0;
  width: 299px;
  height: 100vh;
  background-color: $oyenForum;
  border-left: 2px solid black;
  float: right;

  .header-bar {
    padding: 42px 0px 0px 32px;
    height: 92px;
    border-bottom: 1px solid black;
    display: flex;
    flex-direction: row;
    .friends-icon {
      width: 34px;
      height: 34px;
      background-color: $kuningEternal;
      border: 2px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      border-radius: 5px;
      padding: 3px;
      display: inline-block;
      margin-right: 1rem;
    }

    .header-title {
      margin-top: 5px;
    }

    .search-wrapper {
      margin-top: 5px;
      margin-left: 70px;
    }
  }

  .forum-friends-list {
    padding: 14px 0px 0px 32px;
    display: flex;
    flex-direction: column;
    gap: 32px;

    .friends-wrap {
      .friends-img {
        width: 34px;
        height: 34px;
        border: 2px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 5px;
        margin-right: 1rem;
      }
      .friends-name {
        display: inline-block;
      }
    }
  }
}
</style>
