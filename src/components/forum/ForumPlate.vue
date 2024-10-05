<!-- Forum Box for Forum Page -->

<template>
  <!-- @click="closeSetting" -->
  <div class="forum-plate">
    <div class="top-section">
      <PostSetting v-if="postSetting" />
      <div class="box-header" @click.self="closeSetting">
        <div class="profile-area">
          <img :src="postData.profile" alt="" />
          <div class="profile-identity">
            <p class="post-username">{{ postData.id }}</p>
            <p class="post-time">{{ postData.time }}</p>
          </div>
        </div>
        <div class="box-setting-wrap">
          <span
            class="material-symbols-outlined save-post"
            :class="{ saved: isSaved }"
            @click="toggleSave"
          >
            bookmark
          </span>
          <span
            class="material-symbols-outlined post-setting"
            @click="openSetting"
          >
            more_vert
          </span>
        </div>
      </div>
      <div class="box-content">
        <p class="box-text">
          {{ postData.content }}
        </p>
        <p class="read-more">Read More...</p>
      </div>
      <div class="box-banner">
        <img class="box-img" :src="postData.banner" alt="forum_banner" />
        <div class="post-react">
          <div class="like-wrap">
            <img src="../../assets/img/like_icon.svg" alt="" />
            <span>1</span>
          </div>
          <img src="../../assets/img/forum_comment_icon.svg" alt="" />
          <img src="../../assets/img/forum_share_icon.svg" alt="" />
        </div>
      </div>
    </div>
    <div class="bottom-section">
      <div class="comment-section">
        <div class="user-input-comment">
          <img
            class="user-profile-img"
            src="../../assets/img/profile_ex.svg"
            alt=""
          />
          <input
            class="input-comment"
            type="text"
            placeholder="Write your comment..."
          />
        </div>
        <div class="inputted-comment">
          <img
            class="user-profile-img"
            src="../../assets/img/profile_ex.svg"
            alt=""
          />
          <div class="comment-wrap">
            <div class="inpputed-wrap">
              <p>{{ postData.comment }}</p>
            </div>
            <div class="comment-detail">
              <span>15H</span>
              <span>Like</span>
              <span>Reply</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PostSetting from "./PostSetting.vue";
export default {
  data() {
    return {
      isSaved: false,
      postSetting: false,
    };
  },
  props: ["postData"],
  methods: {
    toggleSave() {
      this.isSaved = !this.isSaved;
    },
    openSetting() {
      this.postSetting = true;
    },
    closeSetting() {
      this.postSetting = false;
    },
  },
  components: { PostSetting },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.forum-plate {
  width: 539px;
  height: auto;
  background-color: $oyenForum;
  border: 3px solid #000000;
  border-radius: 5px;

  .top-section {
    position: relative;
    padding: 13px 20px 12px 20px;
    border-bottom: 1px solid black;

    .box-header {
      display: flex;
      flex-direction: row;
      width: 100%;
      margin-bottom: 10px;

      .profile-area {
        display: flex;
        flex-direction: row;
        padding: 10px;
        border: 2px solid transparent;

        &:hover {
          border: 2px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 5px;
        }

        img {
          width: 42px;
          height: 42px;
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
          border-radius: 2px;
        }

        .profile-identity {
          margin-left: 12px;
          margin-top: 3px;

          p {
            margin: 0;
            padding: 0;
            line-height: 19px;
          }

          .post-username {
            @include font-weight(bold);
          }
          .post-time {
            @include font-weight(medium);
          }
        }
      }

      .box-setting-wrap {
        margin-left: auto;
        padding-top: 10px;
        height: 35px;
        display: flex;
        flex-direction: row;
        gap: 10px;
        span {
          padding: 0;
          margin: 0;
        }

        .saved {
          font-variation-settings: "FILL" 1, "wght" 400, "GRAD" 0, "opsz" 48;
        }
        .save-post {
          cursor: pointer;
        }
        .post-setting {
          cursor: pointer;
        }
      }
    }
    .box-content {
      p {
        @include font-weight(bold);
        line-height: 19px;
      }
    }
    .box-banner {
      display: flex;
      flex-direction: column;
      img {
        max-width: 495px;
        max-height: 301px;
        border-radius: 5px;
      }

      .post-react {
        margin: 10px 10px 0px auto;
        display: flex;
        flex-direction: row;
        gap: 20px;
      }
    }
  }
  .bottom-section {
    padding: 13px 20px 12px 20px;

    .comment-section {
      display: flex;
      flex-direction: column;
      gap: 29px;
      .user-profile-img {
        width: 42px;
        height: 42px;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 2px;
      }

      .user-input-comment {
        display: flex;
        flex-direction: row;
        gap: 13px;

        .input-comment {
          width: 100%;
          height: 33px;
          border-radius: 5px;
          background-color: #eaecf0;
          border: none;
          padding: 0px 0px 0px 10px;
          margin-top: 5px;

          &:focus {
            outline: none;
          }

          &::placeholder {
            color: black;
            @include font-weight(medium);
          }
        }
      }

      .inputted-comment {
        display: flex;
        flex-direction: row;
        gap: 13px;

        .comment-wrap {
          width: 100%;

          .inpputed-wrap {
            width: 100%;
            height: 33px;
            border-radius: 5px;
            background-color: #eaecf0;
            border: none;
            padding: 5px 0px 0px 10px;
            margin-top: 5px;

            p {
              line-height: 20px;
              @include font-weight(medium);
              font-size: 14px;
            }
          }
          .comment-detail {
            display: flex;
            flex-direction: row;
            gap: 10px;
            margin-top: 2px;
            padding-left: 10px;
          }
        }
      }
    }
  }
}
</style>
