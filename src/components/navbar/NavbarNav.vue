<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container">
      <a class="navbar-brand" href="#">
        <img src="@/assets/img/gammon_logo.svg" width="42" height="42" alt="" />
      </a>
      <div class="search">
        <button
          type="button"
          class="search-btn"
          data-bs-toggle="modal"
          data-bs-target="#searchModal"
        >
          <img src="@/assets/img/search_icon.svg" alt="" />
        </button>
      </div>

      <div class="nav-wrapper">
        <div class="navigation-bar" v-if="isForum">
          <a class="navbar-item" href="#">Mobile Legends</a>
          <a class="navbar-item" href="#">PUBG</a>
          <a class="navbar-item" href="#">Free Fire</a>
          <a class="navbar-item" href="#">CODM</a>
        </div>
        <div class="navigation-bar" v-if="isHomepage">
          <router-link class="navbar-item" to="/"> HOME </router-link>
          <router-link class="navbar-item" to="/forum"> FORUM </router-link>
          <a class="navbar-item" href="#">TOURNAMENT</a>
          <a class="navbar-item" href="#">TOP UP</a>
        </div>
      </div>

      <button v-if="isForum" class="showGameModal" @click="toggleGame">
        All Games
      </button>
      <div class="hamburger-btn-wrap" v-if="isForum">
        <button type="button" class="hamburger-btn">
          <span class="material-symbols-outlined" @click="toggleNotif">
            notifications
          </span>
        </button>
        <button type="button" class="hamburger-btn" @click="toggleMenu">
          <span class="material-symbols-outlined"> menu </span>
        </button>
      </div>

      <ProfileMenu v-if="userIsLogin"></ProfileMenu>
      <!-- If User Not Login -->
      <div v-if="isActive" class="btn-wrapper">
        <button type="button" class="login-btn" @click="toggleLoginModal">
          Login
        </button>
        <button type="button" class="sign-up-btn" @click="toggleRegisModal">
          Sign Up
        </button>
      </div>
    </div>
    <!-- If User Login -->
  </nav>
  <LoginModal :showLoginModal="showLogin" @modalClose="toggleLoginModal" />
  <SignUpModal :showRegisModal="showRegis" @modalClose="toggleRegisModal" />
</template>

<script>
import LoginModal from "@/components/modal/LoginModal.vue";
import SignUpModal from "@/components/modal/SignUpModal.vue";
import ProfileMenu from "@/components/profile/ProfileMenu.vue";

export default {
  data() {
    return {
      showLogin: false,
      showRegis: false,
      userIsLogin: true,
      isHomepage: true,
      isForum: false,
      isActive: false,
    };
  },
  emits: ["togglePanel", "toggleNotifForum", "gameList"],
  components: {
    LoginModal,
    SignUpModal,
    ProfileMenu,
  },
  methods: {
    toggleLoginModal() {
      this.showLogin = !this.showLogin;
    },
    toggleRegisModal() {
      this.showRegis = !this.showRegis;
    },
    toggleMenu() {
      this.$emit("togglePanel");
    },
    toggleNotif() {
      this.$emit("toggleNotifForum");
    },
    toggleGame() {
      this.$emit("gameList");
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables";

.container {
  position: relative;
}

nav {
  position: fixed;
  z-index: 1000;
  width: 100%;
  top: 0px;
  overflow: hidden;
  background-color: $primary20;
  height: 65px;
  box-shadow: 2px 2px 0px #000000;

  .navbar-brand {
    position: absolute;
  }
  .navbar-toggler {
    position: absolute;
    right: 0;
  }

  .search {
    position: absolute;
    .search-btn {
      position: relative;
      left: 80px;
      width: 2rem;
      height: 2rem;
      background: none;
      border: none;
      img {
        position: absolute;
        top: 7px;
        left: 0;
        width: 1.2rem;
        position: absolute;
      }
    }
  }
  // .collapse {
  //   margin-inline: auto;
  //   a {
  //     padding-left: 10px;
  //     @include font-weight(bold);
  //     font-size: 0.9rem;
  //     color: black;
  //     text-decoration: none;
  //   }
  // }

  .nav-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;

    .navigation-bar {
      display: flex;
      flex-direction: row;
      gap: 26px;
      margin-inline: auto;
      .navbar-item {
        text-decoration: none;
        color: black;
        @include font-weight(bold);
      }
    }
  }

  .showGameModal {
    position: absolute;
    right: 0;
    margin-right: 290px;
    border: 1px solid #000000;
    box-shadow: 2px 2px 0px #000000;
    border-radius: 2px;
    background-color: $kuningEternal;
    height: 39px;
    width: 98px;
    text-align: center;
    @include font-weight(bold);
  }

  .hamburger-btn-wrap {
    position: absolute;
    right: 0;
    display: flex;
    flex-direction: row;
    gap: 1rem;

    .hamburger-btn {
      width: 44px;
      height: 44px;
      padding: 7px;
      background-color: $kuningEternal;
      border: 2px solid #000000;
      box-shadow: 2px 2px 0px #000000;
      border-radius: 2px;
      span {
        margin: 0;
        padding: 0;
      }
    }
  }
  .disable {
    display: none;
  }
  .btn-wrapper {
    position: absolute;
    right: 0;

    a {
      display: block;
      text-decoration: none;
    }
    .login-btn {
      @extend .btn-master;
      width: 58px;
      height: 29px;
      margin-inline: 5px;
    }
    .sign-up-btn {
      @extend .btn-master;
      background-color: $pinkOCD;
      width: 71px;
      height: 29px;
      margin-inline: 5px;
    }
  }
}
</style>
