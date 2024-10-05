<template>
  <div class="profile-display">
    <img src="../../assets/img/profile_pic_ex.svg" alt="" class="profile-pic" />
    <button type="button" class="change-pic">Change Photo</button>
    <div
      class="follow-wrap"
      :class="{ active: activeToFollowing }"
      @click="toFollowing"
    >
      <p>Following</p>
      <p>390</p>
    </div>
    <div
      class="follow-wrap"
      :class="{ active: activeToFollowers }"
      @click="toFollowers"
    >
      <p>Followers</p>
      <p>459</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeToFollowers: false,
      activeToFollowing: false,
    };
  },
  methods: {
    toFollowers() {
      this.$emit("toFollowers");
      this.activeToFollowers = true;
      this.activeToFollowing = false;
    },
    toFollowing() {
      this.$emit("toFollowing");
      this.activeToFollowing = true;
      this.activeToFollowers = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.profile-display {
  margin-top: 6px;
  display: flex;
  flex-direction: column;
  .profile-pic {
    width: 200px;
    height: 200px;
    border: 1px solid #000000;
    filter: drop-shadow(2px 2px 0px #000000);
    margin-bottom: 20px;
  }
  .change-pic {
    margin-bottom: 30px;
    width: 125px;
    padding-top: 5px;
    padding-bottom: 5px;
    @include font-weight(bold);
    border: 1px solid #000000;
    box-shadow: 2px 2px 0px #000000;
    background-color: $kuningEternal;
  }

  .follow-wrap {
    cursor: pointer;
    display: flex;
    flex-direction: row;
    gap: 26px;
    background-color: $kuningSummer;
    width: 150px;
    @include font-weight(bold);
    margin-bottom: 25px;
    padding-top: 10px;
    padding-left: 10px;
  }
  .active {
    border: 2px solid #000000;
    box-shadow: 2px 2px 0px #000000;
  }
}
</style>
