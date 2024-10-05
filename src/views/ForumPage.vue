<template>
  <NavbarNav
    @togglePanel="toggleMenu"
    @toggleNotifForum="toggleNotifMenu"
    @gameList="toggleList"
  />
  <ListGames v-if="gameList" />
  <div class="forum-body">
    <CreatePostModal v-if="createPost" @close="toggleCreate" />
    <LeftBar :forumData="groups" />
    <GroupPage v-if="!inAnotherGroup" :inGroup="groups" />
    <div v-if="inAnotherGroup" class="forum-home">
      <div class="up-post-wrap" @click="toggleCreate">
        <img class="post-img" src="../assets/img/user_profile_img.svg" alt="" />
        <div class="text-wrap">
          <p>Make a new post</p>
        </div>
      </div>
      <div class="forum-plate-wrapper">
        <div v-for="post in forumPost" :key="post.id" class="post-wrap">
          <ForumPlate :postData="post" />
        </div>
      </div>
    </div>
    <RightBar />
    <MenuPanel v-if="panelOpened" />
    <NotifPanel v-if="notifOpened" />
  </div>
</template>

<script>
import NavbarNav from "@/components/navbar/NavbarNav.vue";
import LeftBar from "../components/forum/LeftBar.vue";
import RightBar from "../components/forum/RightBar.vue";
import GroupPage from "../components/forum/GroupPage.vue";
import ForumPlate from "@/components/forum/ForumPlate.vue";
import CreatePostModal from "@/components/forum/CreatePostModal.vue";
import MenuPanel from "@/components/forum/MenuPanel.vue";
import NotifPanel from "@/components/forum/NotifPanel.vue";
import ListGames from "@/components/forum/ListGames.vue";
export default {
  data() {
    return {
      createPost: false,
      inAnotherGroup: true,
      panelOpened: false,
      notifOpened: false,
      gameList: false,
      groups: [
        {
          id: "Mencret Abis bray",
          img: require("@/assets/img/user_follow_pic_ex.svg"),
        },
        {
          id: "Sembah Wisnuuu!",
          img: require("@/assets/img/user_profile_img.svg"),
        },
      ],
      forumPost: [
        {
          id: "Wisnu Gondrong",
          time: "1 hours ago",
          content: "Mantap ada hero baru ya ges ya",
          profile: require("@/assets/img/user_profile_img.svg"),
          banner: require("@/assets/img/hero_ex.svg"),
          comment: "Mantap coyhhh",
        },
        {
          id: "Blek Hitam",
          time: "4 hours ago",
          content: "Cari lawan mek",
          profile: require("@/assets/img/user_default_img.svg"),
          banner: require("@/assets/img/hero_ex.svg"),
          comment: "gassss coy",
        },
        {
          id: "Paiz kang galau",
          time: "5 hours ago",
          content: "WTS Akun Valo full skin",
          profile: require("@/assets/img/user_profile_img.svg"),
          banner: require("@/assets/img/hero_ex.svg"),
          comment: "500k lepas ga bang?",
        },
        {
          id: "Paceee euy",
          time: "8 hours ago",
          content: "OTW MPL 2023",
          profile: require("@/assets/img/user_profile_img.svg"),
          banner: require("@/assets/img/hero_ex.svg"),
          comment: "Gas join streaming skrg",
        },
        {
          id: "Bimonyong",
          time: "9 hours ago",
          content: "Eeeh apaantu",
          profile: require("@/assets/img/user_profile_img.svg"),
          banner: require("@/assets/img/hero_ex.svg"),
          comment: "apatu?",
        },
      ],
    };
  },
  components: {
    LeftBar,
    RightBar,
    GroupPage,
    ForumPlate,
    CreatePostModal,
    MenuPanel,
    NavbarNav,
    NotifPanel,
    ListGames,
  },
  methods: {
    toggleCreate() {
      this.createPost = !this.createPost;
    },
    toggleMenu() {
      this.panelOpened = !this.panelOpened;
    },
    toggleNotifMenu() {
      this.notifOpened = !this.notifOpened;
    },
    toggleList() {
      this.gameList = !this.gameList;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";
.forum-body {
  position: relative;
  top: 2px;
  width: min(100vw);
  height: min(93.3vh);
  background-color: $kuningEternal;
  display: flex;
  flex-direction: row;
  margin-top: 4rem;

  .forum-home {
    margin-top: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-inline: auto;
    width: 100%;
    gap: 25px;

    .up-post-wrap {
      display: flex;
      flex-direction: row;
      padding: 15px;
      width: 539px;
      background-color: $oyenForum;
      border: 2px solid #000000;
      border-radius: 5px;
      margin-inline: auto;
      cursor: pointer;
      gap: 6px;

      .post-img {
        width: 42px;
        height: 42px;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 5px;
      }

      .text-wrap {
        width: 460px;
        height: 41px;
        background-color: $kuningEternal;
        border: 2px solid rgba(0, 0, 0, 0.5);
        border-radius: 5px;

        p {
          color: rgba(0, 0, 0, 0.5);
          line-height: 20px;
          padding-left: 10px;
          padding-top: 7px;
          @include font-weight(semibold);
        }
      }
    }

    .forum-plate-wrapper {
      display: flex;
      margin-inline: auto;
      gap: 71px;
      flex-direction: column;
      overflow: auto;
      // height: min(90vh);
      &::-webkit-scrollbar {
        display: none;
        overflow: hidden;
      }
    }
  }
}
</style>
