<template>
  <div class="backdrop" @click.self="handleClose">
    <div class="modal-box">
      <div class="box-header">
        <div class="top">
          <button class="close-modal">
            <span class="material-symbols-outlined" @click.self="handleClose">
              close
            </span>
          </button>
          <h5 class="title">Create Post</h5>
        </div>
        <div class="bottom">
          <div class="category-dropdown">
            <span>Category</span>
            <span class="material-symbols-outlined"> keyboard_arrow_down </span>
          </div>
        </div>
      </div>
      <div class="box-body">
        <form action="">
          <div class="text-area">
            <textarea
              class="input-area"
              name=""
              id=""
              placeholder="Enter Text..."
              cols="30"
              rows="10"
            ></textarea>
            <label for="image" class="input-image">
              <input id="image" type="file" accept="image/png, image/jpeg" />
              <span class="material-symbols-outlined">
                add_photo_alternate
              </span>
            </label>
          </div>
          <button type="submit" class="submit-btn">Send</button>
        </form>
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
@import "@/assets/scss/variables.scss";
.backdrop {
  position: fixed;
  top: 0;
  background-color: rgba(0, 0, 0, 0.1);
  width: 100%;
  height: 100%;
  z-index: 200999;
  display: flex;
  align-items: center;
  justify-content: center;

  .modal-box {
    position: relative;
    width: 539px;
    height: 392px;
    border: 2px solid #000000;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 5px;
    background: $kuningEternal;
    margin-inline: auto;
    padding: 14px 16px 12px 16px;

    .box-header {
      display: flex;
      flex-direction: column;

      .top {
        display: flex;
        flex-direction: row;

        .close-modal {
          width: 34px;
          height: 34px;
          border: 2px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 5px;
          padding: 0;
          background-color: $oyenForum;

          span {
            text-align: center;
            padding: 0;
            margin-top: 3px;
          }
        }

        .title {
          margin-inline: auto;
          margin-top: 9px;
          font-size: 1rem;
          @include font-weight(bold);
        }
      }
      .bottom {
        display: flex;
        flex-direction: row;
        margin-left: auto;
        .category-dropdown {
          display: flex;
          flex-direction: row;
          background: $oyenForum;
          @include font-weight(medium);
          padding: 5px 9px;
          border: 1px solid #000000;
          border-radius: 5px;
        }
      }
    }
    .box-body {
      position: relative;
      width: 100%;
      .text-area {
        position: relative;
        width: 100%;
        margin-top: 25px;
        height: 227px;
        background-color: #fff;
        border: 2px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 8px;
        padding: 10px 14px 0px 14px;
        .input-area {
          width: 100%;
          max-height: 85%;
          border-radius: 8px;
          border: none;

          &:focus {
            outline: none;
          }
        }

        input[type="file"] {
          display: none;
        }

        .input-image {
          position: absolute;
          cursor: pointer;
          bottom: 0;
          right: 9px;

          span {
            font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 48;
            font-size: 40px;
          }
        }
      }
      .submit-btn {
        position: absolute;
        font-size: 12px;
        @include font-weight(semibold);
        background-color: $oyenForum;
        padding: 4px 0px;
        right: 0;
        width: 117px;
        margin-top: 12px;
        border: 2px solid #000000;
        border-radius: 5px;
      }
    }
  }
}
</style>
