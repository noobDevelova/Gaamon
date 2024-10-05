<template>
  <div class="saved-box">
    <div class="box-header">
      <h3>Saved</h3>
      <router-link to="/" class="close-button">
        <span class="material-symbols-outlined"> close </span>
      </router-link>
    </div>
    <div class="box-body">
      <div class="current-display-box">
        <div class="current-box">ALL</div>
        <button class="button-add" type="button">
          <span class="material-symbols-outlined"> add_circle </span>
        </button>
      </div>
      <div class="saved-content-wrap">
        <div v-for="save in saves" :key="save" class="saved">
          <img class="saved-img" :src="save.img" alt="" />
        </div>
        <div class="add-saved">
          <span class="material-symbols-outlined"> add_circle </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      saves: [
        {
          img: require("@/assets/img/saved_ex.svg"),
        },
        {
          img: require("@/assets/img/saved2_ex.svg"),
        },
        {
          img: require("@/assets/img/saved3_ex.svg"),
        },
        {
          img: require("@/assets/img/saved4_ex.svg"),
        },
        {
          img: require("@/assets/img/saved2_ex.svg"),
        },
        {
          img: require("@/assets/img/saved5_ex.svg"),
        },
        {
          img: require("@/assets/img/saved6_ex.svg"),
        },
        {
          img: require("@/assets/img/saved3_ex.svg"),
        },
        {
          img: require("@/assets/img/saved4_ex.svg"),
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.saved-box {
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

    .current-display-box {
      display: flex;
      flex-direction: row;
      gap: 15px;

      .current-box {
        background-color: $kuningEternal;
        border: 1px solid #000000;
        width: 120px;
        height: 40px;
        box-shadow: 2px 2px 0px #000000;
        line-height: 13px;
        padding: 13px 0px 13px 10px;
        @include font-weight(bold);
        font-size: 12px;
      }

      .button-add {
        display: flex;
        justify-content: center;
        width: 40px;
        height: 40px;
        margin: 0;
        padding: 0;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 2px;
        background-color: $kuningEternal;
        span {
          margin-top: 4.5px;
          font-size: 30px;
        }
      }
    }

    .saved-content-wrap {
      display: grid;
      grid-template-columns: auto auto auto auto;
      row-gap: 50px;
      column-gap: auto;
      width: 100%;
      height: 480px;
      overflow: auto;
      .saved {
        width: 200px;
        height: 200px;
        .saved-img {
          width: 200px;
          height: 200px;
          border: 1px solid #000000;
          filter: drop-shadow(2px 2px 0px #000000);
        }
      }
      .add-saved {
        width: 200px;
        height: 200px;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        position: relative;
        span {
          position: absolute;
          top: 35%;
          left: 35%;
          font-size: 60px;
        }
      }
    }
  }
}
</style>
