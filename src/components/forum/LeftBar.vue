<template>
  <aside class="left-bar">
    <h1 class="heading">Forum</h1>
    <div class="group-forum-wrapper">
      <div class="profile-forum">
        <img
          class="group-profile"
          src="../../assets/img/user_profile_img.svg"
          alt="group_profile"
        />
        <p class="group-name">Randi Risdiansyah</p>
      </div>
      <div class="profile-icon">
        <div class="group-icon">
          <span class="material-symbols-outlined"> group </span>
        </div>
        <p class="group-name">My Group</p>
      </div>
      <div v-for="group in forumData" :key="group.id">
        <div class="profile-forum">
          <img class="group-profile" :src="group.img" alt="group_profile" />
          <p class="group-name">{{ group.id }}</p>
        </div>
      </div>
    </div>
  </aside>
</template>

<script>
export default {
  props: ["forumData"],
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.left-bar {
  position: fixed;
  width: 408px;
  background-color: $oyenForum;
  height: 100vh;
  padding: 44px 0px 0px 71px;
  border-right: 2px solid black;
  z-index: 10000;

  .heading {
    font-size: 1.9rem;
    @include font-weight(bold);
    margin-left: 11px;
  }

  .group-forum-wrapper {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 40px;
    .profile-forum {
      padding: 10px 0px 10px 15px;
      border: 2px solid transparent;
      width: 275px;
      transition: all 0.2s ease-in-out;

      &:hover {
        border: 2px solid black;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 5px;
        transition: all 0.2s ease-in-out;
      }
      .group-profile {
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px black;
        border-radius: 2px;
        width: 38px;
        height: 38px;
      }
      .group-name {
        display: inline;
        margin-left: 1rem;
        @include font-weight(bold);
      }
    }
    .profile-icon {
      display: flex;
      flex-direction: row;
      width: auto;
      height: 39px;
      gap: 1.1rem;
      padding: 10px 0px 10px 15px;
      height: 62px;
      border: 2px solid transparent;
      width: 275px;
      .group-profile {
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px black;
        border-radius: 2px;
      }
      .group-icon {
        border: 2px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 2px;
        width: 39px;
        height: 39px;
        padding: 5px;
        background-color: $kuningEternal;
      }
      .group-name {
        @include font-weight(bold);
        margin-top: 0.4rem;
      }
    }
  }
}
</style>
