<template>
  <div class="wrapper">
    <div
      class="chat-frame"
      :class="{ notExpanded: notExpanded, expanded: expanded }"
    >
      <img
        src="../../assets/img/chitchat_icon.svg"
        alt="chitchat_logo"
        @click="toggleExpand"
      />
      <button
        v-if="expanded"
        type="button"
        class="close-chat"
        @click="closeExpand"
      >
        <span class="material-symbols-outlined"> close </span>
      </button>
      <div class="search-wrapper">
        <img
          class="search-icon"
          src="../../assets/img/search_icon.svg"
          alt=""
        />
        <input class="search" type="text" />
        <span class="place">Search</span>
      </div>
      <div class="chat-inner-content">
        <div class="chat-friends" :class="{ hide: notExpanded }">
          <span class="profile-chat-wrapper"
            ><img src="../../assets/img/chat_profile_ex.svg" alt=""
          /></span>
          <span class="profile-chat-wrapper"
            ><img src="../../assets/img/chat_profile_ex.svg" alt=""
          /></span>
          <span class="profile-chat-wrapper"
            ><img src="../../assets/img/chat_profile_ex.svg" alt=""
          /></span>
          <span class="profile-chat-wrapper"
            ><img src="../../assets/img/chat_profile_ex.svg" alt=""
          /></span>
          <button type="button" class="add-chat">
            <img src="../../assets/img/plus_circle_icon.svg" alt="" />
          </button>
        </div>
        <div class="chat-box" :class="{ hide: notExpanded }">
          <div class="inner-personal-chat">
            <div class="pop-chat-plate"></div>
          </div>
          <!-- Group Chat -->
          <div v-if="chatGroup" class="inner-chat-wrap">
            <div v-for="chat in chats" :key="chat.id" class="pop-chat-plate">
              <p class="chat-text">{{ chat.text }}</p>
              <div class="user-chat-img-wrapper">
                <img
                  class="chat-user-profile"
                  :src="chat.img"
                  alt="user_img_profile"
                />
              </div>
            </div>
          </div>
          <div class="input-message-wrap">
            <img
              class="current-user-chat-img"
              src="../../assets/img/user_chat_ex.svg"
              alt="chat_profile"
            />
            <input
              class="input-message"
              type="text"
              placeholder="Write a text..."
            />
            <button type="button" class="send-button">
              <img
                src="../../assets/img/send_message_icon.svg"
                alt="send_icon"
              />
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      notExpanded: true,
      expanded: false,
      chatGroup: true,
      chats: [
        {
          text: "mabar yokk",
          id: 1,
          img: require("@/assets/img/user_profile_img.svg"),
        },
        {
          text: "mana gajadi?",
          id: 2,
          img: require("@/assets/img/user_default_img.svg"),
        },
        {
          text: "skip bro mau ngaji",
          id: 3,
          img: require("@/assets/img/user_follow_pic_ex.svg"),
        },
        {
          text: "palkorrrr",
          id: 4,
          img: require("@/assets/img/user_chat_ex.svg"),
        },
      ],
    };
  },
  methods: {
    toggleExpand() {
      this.notExpanded = false;
      this.expanded = true;
    },
    closeExpand() {
      this.notExpanded = true;
      this.expanded = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.expanded {
  position: absolute;

  height: 620px;
}
.not-expanded {
  height: 120px;
}
.chat-frame {
  width: 380px;
  background-color: $merahCrimson;
  border: 1px solid #000000;
  box-shadow: 2px 2px 0px #000000;
  padding: 10px;

  .close-chat {
    position: absolute;
    margin-right: 10px;
    right: 0;
    width: 20px;
    height: 20px;
    background-color: $merahCrimson;
    border: 1px solid #000000;
    box-shadow: 2px 2px 0px #000000;
    padding: 0px;

    span {
      position: absolute;
      top: -2px;
      left: -2px;
      font-size: 21px;
    }
  }

  .search-wrapper {
    position: relative;
    margin-top: 19px;

    .search-icon {
      position: absolute;
      margin: 6px;
      margin-left: 10px;
      width: 16px;
      height: 16px;
    }
    .place {
      position: absolute;
      width: 100px;
      left: 0;
      right: 0;
      margin-inline: auto;
      text-align: center;
    }
    .search {
      width: 100%;
      border: 1px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      border-radius: 2px;
      background-color: $merahCrimson;
      padding-left: 40px;
      &:focus ~ .place {
        text-align: left;
      }
    }
    .search:focus ~ .place {
      display: none;
    }
  }
  .chat-inner-content {
    position: relative;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 18px;

    .chat-friends {
      display: flex;
      flex-direction: column;
      gap: 10px;
      .profile-chat-wrapper {
        img {
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
        }
      }
      .add-chat {
        background-color: $merahCrimson;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        width: 32px;
        height: 32px;
        img {
          margin: 0;
          padding: 0;
        }
      }
    }

    .hide {
      display: none;
    }

    .chat-box {
      width: 315px;
      height: 500px;
      background-color: $neutral;
      border: 1px solid black;
      box-shadow: 2px 2px 0px black;
      padding: 10px 10px 15px 10px;
      .inner-chat-wrap {
        display: flex;
        flex-direction: column;
        gap: 8px;
        height: 430px;
        overflow: auto;
        .pop-chat-plate {
          display: flex;
          margin-left: auto;
          gap: 15px;
          border: 1px solid black;
          width: fit-content;
          padding-inline: 10px;
          padding-top: 7px;
          padding-bottom: 6px;

          p {
            margin: 0;
            padding: 0;
          }

          .chat-text {
            @include font-weight(medium);
            font-size: 0.9rem;
            margin-top: 2px;
          }

          .user-chat-img-wrapper {
            .chat-user-profile {
              width: 22px;
              height: 22px;
              border: 1px solid #000000;
              box-shadow: 2px 2px 0px #000000;
            }
          }
        }
      }

      .input-message-wrap {
        position: absolute;
        bottom: 15px;
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: 5px;
        .input-message {
          height: 30px;
          background: $neutral;
          border: 1px solid black;
          padding-left: 5px;

          &:focus {
            outline: none;
          }
          &::placeholder {
            @include font-weight(medium);
          }
        }

        .current-user-chat-img {
          width: 30px;
          height: 30px;
          border: 1px solid #000000;
          box-shadow: 2px 2px 0px #000000;
        }

        .send-button {
          border: none;
          background-color: $neutral;
        }
      }
    }
  }
}
</style>
