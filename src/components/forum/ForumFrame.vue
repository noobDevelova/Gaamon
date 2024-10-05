<template>
  <div class="forum-plate">
    <div class="header-wrap">
      <slot name="profile">
        <div class="profile-plate">
          <img
            class="forum-profile-img"
            src="../../assets/img/profile_ex.svg"
            alt="profile_img"
          />
          <div class="profile-area">
            <p class="username-forum-plate">Robert Iwan</p>
            <p class="user-post-time">2 hours ago</p>
          </div>
        </div>
      </slot>
      <div class="header-set">
        <span class="material-symbols-outlined"> bookmark </span>
        <span class="material-symbols-outlined"> more_vert </span>
      </div>
    </div>
    <slot name="forum-text-content">
      <div class="forum-text-content">
        <p class="forum-text-isi">
          Para Coach SEA Games Bergabung ke Akademi Garudaku!
        </p>
        <p class="read-more">Read More...</p>
      </div>
    </slot>
    <slot name="forum-img-banner"
      ><div class="forum-img-banner">
        <img
          class="forum-img"
          src="../../assets/img/forum_banner_ex.svg"
          alt="forum_banner"
        />
        <div class="forum-post-react">
          <div class="like-wrapper">
            <img src="../../assets/img/like_icon.svg" alt="like_icon" />
            <p>1</p>
          </div>
          <img
            class="content-btn"
            src="../../assets/img/forum_comment_icon.svg"
            alt="comment_icon"
          />
          <img src="../../assets/img/forum_share_icon.svg" alt="share_icon" />
        </div></div
    ></slot>
    <div class="forum-comment-section">
      <slot name="comment-section"
        ><div class="input-comment-wrapper">
          <img
            class="user-profile-comment"
            src="../../assets/img/profile_ex.svg"
            alt="img_comment"
          />
          <input
            class="user-input-comment"
            type="text"
            placeholder="Write your comment..."
          /></div
      ></slot>
      <slot name="user-is-comment">
        <div class="user-is-comment">
          <img
            class="user-profile-comment"
            src="../../assets/img/profile_ex.svg"
            alt="img_comment"
          />
          <div class="inputted-comment">
            <p>hilihhh kinthilll</p>
            <div class="comment-react">
              <span>15H</span>
              <span>Like</span>
              <span>Reply</span>
            </div>
          </div>
        </div>
      </slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.forum-plate {
  background-color: $oyenForum;
  width: 539px;
  height: 672px;
  border: 3px solid #000000;
  border-radius: 5px;

  .header-wrap {
    padding: 10px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-inline: 5px;
    margin-top: 10px;
  }
  .header-set {
    display: flex;
    flex-direction: row;
    gap: 20px;
  }
}
.profile-plate {
  display: flex;
  flex-direction: row;
  gap: 13px;

  .forum-profile-img {
    width: 42px;
    height: 42px;
    border: 1px solid black;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 2px;
  }

  .profile-area {
    display: inline-block;

    p {
      margin: 0;
      padding: 0;
    }

    .username-forum-plate {
      @include font-weight(bold);
      font-family: $archivo;
    }
    .user-post-time {
      @include font-weight(medium);
      font-size: 14px;
      font-family: $archivo;
    }
  }
}
.profile-plate {
  display: flex;
  flex-direction: row;
  gap: 13px;

  .forum-profile-img {
    width: 42px;
    height: 42px;
    border: 1px solid black;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 2px;
  }

  .profile-area {
    display: inline-block;

    p {
      margin: 0;
      padding: 0;
    }

    .username-forum-plate {
      @include font-weight(bold);
      font-family: $archivo;
    }
    .user-post-time {
      @include font-weight(medium);
      font-size: 14px;
      font-family: $archivo;
    }
  }
}
.forum-text-content {
  padding-inline: 10px;
  margin-inline: 5px;
  margin-top: 15px;

  .forum-text-isi {
    @include font-weight(bold);
  }

  .read-more {
    @extend .forum-text-isi;
  }
}

.forum-img-banner {
  margin-inline: 20px;
  .forum-img {
    border-radius: 5px;
  }
  .forum-post-react {
    margin-top: 10px;
    margin-bottom: 10px;
    margin-right: 5px;
    display: flex;
    margin-left: auto;
    justify-content: flex-end;
    .like-wrapper,
    img,
    p {
      display: inline-block;
      margin: 0;
      padding: 0;
    }
    p {
      font-family: $archivo;
      @include font-weight(medium);
      font-size: 14px;
      margin-left: 2px;
    }
    .like-wrapper {
      margin-right: 20px;
    }
    .content-btn {
      margin-right: 20px;
    }
  }
}
.user-input-comment {
  margin-left: 15px;
  padding: 10px;
  width: 88%;
  border-radius: 5px;
  border: 1px solid black;
  height: 33px;
  box-shadow: 2px 2px 0px #000000;

  &:focus {
    outline: none;
  }
  &::placeholder {
    color: black;
    font-family: $archivo;
    @include font-weight(medium);
    font-size: 14px;
  }
}
.user-profile-comment {
  box-shadow: 2px 2px 0px #000000;
  border: 1px solid black;
}

.user-input-comment[type="text"] {
  color: black;
  font-family: $archivo;
  @include font-weight(medium);
  font-size: 14px;
}
.user-is-comment {
  margin-top: 25px;
  display: flex;
  flex-direction: row;
  gap: 15px;
  .user-profile-comment {
    box-shadow: 2px 2px 0px #000000;
    border: 1px solid black;
  }
  .inputted-comment {
    width: 88%;
    background-color: #fff;
    height: 33px;
    border-radius: 5px;
    margin-top: 2px;
    border: 1px solid black;
    box-shadow: 2px 2px 0px #000000;

    p {
      margin: 0;
      padding: 0;
      color: black;
      font-family: $archivo;
      @include font-weight(medium);
      font-size: 14px;
      padding-top: 5px;
      padding-left: 10px;
    }
    .comment-react {
      margin-top: 10px;
      margin-left: 10px;
      display: flex;
      flex-direction: row;
      gap: 10px;

      span {
        @include font-weight(semibold);
        font-size: 15px;
      }
    }
  }
}
.forum-comment-section {
  padding-inline: 20px;
  padding-top: 13px;
  border-top: 1px solid black;
}
</style>
