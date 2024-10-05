<template>
  <aside class="notif-panel">
    <h3 class="title">Notification</h3>
    <ul v-for="notif in notifs" :key="notif.name" class="notif-wrap">
      <li class="notif-item">
        <div class="img-wrapper">
          <img :src="notif.img" alt="notif_profile" />
        </div>
        <div class="desc-wrapper">
          <p class="notif-name">
            {{ notif.name }} <span class="notif-desc">{{ notif.desc }}</span>
          </p>
          <p class="notif-date">{{ notif.date }}</p>
        </div>
      </li>
    </ul>
  </aside>
</template>

<script>
export default {
  data() {
    return {
      notifs: [
        {
          name: "Blek",
          img: require("@/assets/img/user_profile_img.svg"),
          desc: "Has following you.",
          date: "2 hours ago",
        },
        {
          name: "Wisnu",
          img: require("@/assets/img/user_profile_img.svg"),
          desc: "Like Your Post.",
          date: "1 hours ago",
        },
        {
          name: "Pace",
          img: require("@/assets/img/user_chat_ex.svg"),
          desc: "Tagged you in post.",
          date: "7 hours ago",
        },
        {
          name: "Jupri",
          img: require("@/assets/img/user_follow_pic_ex.svg"),
          desc: "Make a new post.",
          date: "9 hours ago",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables.scss";

.notif-panel {
  position: fixed;
  right: 0;
  width: 299px;
  height: auto;
  background-color: $kuningSummer;
  border-left: 2px solid black;
  float: right;
  padding: 23px 18px;
  border-bottom: 2px solid black;

  .title {
    font-size: 24px;
    @include font-weight(bold);
    margin-left: 25px;
  }

  .notif-wrap {
    display: flex;
    flex-direction: column;
    gap: 14px;
    padding: 0;

    .notif-item {
      display: flex;
      flex-direction: row;
      align-items: center;
      padding: 7px 22px;
      border: 2px solid transparent;
      gap: 14px;
      background-color: $kuningEternal;

      &:hover {
        border: 2px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 5px;
      }

      p {
        line-height: 13px;
        margin: 0;
      }

      .img-wrapper {
        img {
          width: 40px;
          border-radius: 50px;
        }
      }
      .notif-name {
        font-size: 12px;
        @include font-weight(semibold);

        .notif-desc {
          color: $placeholder;
          font-size: 10px;
        }
      }
      .notif-date {
        font-size: 10px;
        @include font-weight(semibold);
      }
    }
  }
}
</style>
