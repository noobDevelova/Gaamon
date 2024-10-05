<template>
  <div class="profile-header">
    <div class="profile-pic-wrapper">
      <img src="../../assets/img/user_profile_img.svg" alt="" />
    </div>
    <div class="profile-name">
      <p class="profile-username">Randi Risdiansyah</p>
      <p class="profile-email">randyrisdiansyah@gmail.com</p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.profile-header {
  display: flex;
  gap: 1rem;

  p {
    margin: 0;
  }

  .profile-username {
    @include font-weight(bold);
    font-size: 1.1rem;
  }
  .profile-email {
    @include font-weight(bold);
    font-size: 1.1rem;
  }
  .profile-pic-wrapper {
    img {
      border: 1px solid black;
      filter: drop-shadow(2px 2px 0px #000000);
      width: 50px;
      height: 50px;
    }
  }
}
</style>
