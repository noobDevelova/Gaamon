<template>
  <div class="my-group">
    <div class="my-group-header">
      <div class="my-container">
        <div v-for="group in inGroup" :key="group">
          <img class="my-group-img" :src="group.img" alt="" />
          <p class="my-group-name">{{ group.id }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["inGroup"],
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.my-container {
  width: 57%;
  margin-inline: auto;
}

.my-group {
  width: 100%;
  position: relative;

  .my-group-header {
    width: 100%;
    margin-inline: auto;
    height: 62px;
    background-color: $oyenForum;
    border-bottom: 1px solid black;
    padding: 12px 0px 12px 15px;

    .my-container {
      display: flex;
      flex-direction: row;

      .my-group-img {
        width: 38px;
        height: 38px;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 2px;
      }

      .my-group-name {
        margin-left: 1rem;
        @include font-weight(bold);
        font-size: 20px;
        margin-top: 4px;
      }
    }
  }
}
</style>
