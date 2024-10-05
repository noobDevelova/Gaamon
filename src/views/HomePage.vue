<template>
  <NavbarNav />
  <div class="page-body">
    <div class="container">
      <h1 class="home-heading">Event Trend</h1>
      <div class="hero-wrapper">
        <HeroFrame class="home-hero">
          <img
            class="img-banner"
            src="../assets/img/hero_ex.svg"
            alt="hero_img"
          />
          <p class="hero-content">
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Itaque quo
            quae necessitatibus in qui.
          </p>
        </HeroFrame>
        <div v-if="isLogin" class="side-right-wrapper">
          <MonPayHome></MonPayHome>
          <ChatDynamic></ChatDynamic>
        </div>
        <ChatFrame v-else class="chat-static">
          <template v-slot:search>
            <div class="search-wrapper">
              <span class="material-symbols-outlined search-icon">
                search
              </span>
              <input type="text" class="search-input" placeholder="Search" />
            </div>
          </template>
          <template v-slot:chat>
            <div class="chat-box">
              <div class="chat-box-wrapper">
                <div class="chat-pop-wrap">
                  <div class="pop-chat-plate">
                    <p class="chat-text">Haloo Broo!!!!</p>
                    <div class="user-chat-img-wrapper">
                      <img
                        class="chat-user-profile"
                        src="../assets/img/user_chat_ex.svg"
                        alt="user_img_profile"
                      />
                    </div>
                  </div>
                </div>
                <div class="chat-pop-wrap">
                  <div class="pop-chat-plate user-is-login">
                    <p class="chat-text">
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                      Expedita, consequuntur?
                    </p>
                    <div class="user-chat-img-wrapper">
                      <img
                        class="chat-user-profile"
                        src="../assets/img/user_chat_ex.svg"
                        alt="user_img_profile"
                      />
                    </div>
                  </div>
                </div>
                <div class="chat-pop-wrap">
                  <div class="pop-chat-plate">
                    <p class="chat-text">Lorem ipsum dolor sit amet.</p>
                    <div class="user-chat-img-wrapper">
                      <img
                        class="chat-user-profile"
                        src="../assets/img/user_chat_ex.svg"
                        alt="user_img_profile"
                      />
                    </div>
                  </div>
                </div>
                <div class="chat-pop-wrap">
                  <div class="pop-chat-plate user-is-login">
                    <p class="chat-text">
                      Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                      Laudantium, nobis.
                    </p>
                    <div class="user-chat-img-wrapper">
                      <img
                        class="chat-user-profile"
                        src="../assets/img/user_chat_ex.svg"
                        alt="user_img_profile"
                      />
                    </div>
                  </div>
                </div>
                <div class="chat-pop-wrap">
                  <div class="pop-chat-plate">
                    <p class="chat-text">
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                      Iste, harum non.
                    </p>
                    <div class="user-chat-img-wrapper">
                      <img
                        class="chat-user-profile"
                        src="../assets/img/user_chat_ex.svg"
                        alt="user_img_profile"
                      />
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </template>
        </ChatFrame>
      </div>

      <div class="featured">
        <div class="featured-forum">
          <h1 class="home-heading">Featured Forum</h1>
          <div class="forum-plate-wrapper">
            <div class="plate-wrap">
              <ForumFrame> </ForumFrame>
            </div>
            <div class="plate-wrap">
              <ForumFrame> </ForumFrame>
            </div>
            <div class="plate-wrap">
              <ForumFrame> </ForumFrame>
            </div>
          </div>
        </div>

        <div class="featured-tournament">
          <h1 class="home-heading">Featured Tournament</h1>
          <div class="banner-frame-wrapper">
            <div class="frame-wrap">
              <TournamentBanner>
                <template v-slot:banner-img>
                  <img
                    src="../assets/img/tour_banner_ex.svg"
                    alt="tournament_banner"
                  />
                </template>
                <template v-slot:banner-title>
                  <p class="banner-text">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  </p>
                </template>
              </TournamentBanner>
            </div>
            <div class="frame-wrap">
              <TournamentBanner>
                <template v-slot:banner-img>
                  <img
                    src="../assets/img/tour_banner_ex.svg"
                    alt="tournament_banner"
                  />
                </template>
                <template v-slot:banner-title>
                  <p class="banner-text">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  </p>
                </template>
              </TournamentBanner>
            </div>
            <div class="frame-wrap">
              <TournamentBanner>
                <template v-slot:banner-img>
                  <img
                    src="../assets/img/tour_banner_ex.svg"
                    alt="tournament_banner"
                  />
                </template>
                <template v-slot:banner-title>
                  <p class="banner-text">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  </p>
                </template>
              </TournamentBanner>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeroFrame from "@/components/HeroFrame.vue";
import ChatFrame from "@/components/chitchat/ChatFrame.vue";
import ForumFrame from "@/components/forum/ForumFrame.vue";
import TournamentBanner from "@/components/tournament/TournamentBanner.vue";
import MonPayHome from "@/components/monpay/MonPayHome.vue";
import ChatDynamic from "@/components/chitchat/ChatDynamic.vue";
import NavbarNav from "@/components/navbar/NavbarNav.vue";

export default {
  data() {
    return {
      isLogin: true,
    };
  },

  components: {
    HeroFrame,
    ChatFrame,
    ForumFrame,
    TournamentBanner,
    MonPayHome,
    ChatDynamic,
    NavbarNav,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";
.page-body {
  width: min(100vw);
  height: min(100vh);
  background-color: $primary20;
  padding-top: 60px;
}
.home-heading {
  padding-top: 25px;
  margin-bottom: 10px;
  font-size: 20px;
  @include font-weight(bold);
}
.hero-wrapper {
  display: flex;
  flex-direction: row;
  gap: 30px;

  .home-hero {
    .img-banner {
      width: 100%;
    }
    .hero-content {
      @include font-weight(bold);
      margin-top: 10px;
      text-align: center;
    }
  }
  .side-right-wrapper {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  .chat-static {
    .search-wrapper {
      margin-top: 1rem;
      position: relative;

      .search-icon {
        position: absolute;
      }

      .search-input {
        width: 100%;
        background-color: $merahGelap;
        border: 1px solid #000000;
        box-shadow: 2px 2px 0px #000000;
        border-radius: 2px;
        text-align: center;

        &:focus {
          outline: none;
        }

        &::placeholder {
          text-align: center;
          color: black;
        }
      }
    }

    .chat-box {
      margin-top: 1rem;
      padding: 10px;
      width: 100%;
      height: 240px;
      background-color: $greySolid;
      border: 1px solid #000000;
      box-shadow: 2px 2px 0px #000000;

      .chat-box-wrapper {
        height: 220px;
        display: flex;
        gap: 8px;
        flex-direction: column;
        overflow: auto;

        &::-webkit-scrollbar {
          display: none;
        }
        .chat-pop-wrap {
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
                border: 1px solid #000000;
                box-shadow: 2px 2px 0px #000000;
              }
            }
          }
          .user-is-login {
            background-color: $ijoSampah;
          }
        }
      }
    }
  }
}
.featured {
  display: flex;
  flex-direction: row;
  gap: 71px;
  .featured-forum {
    display: flex;
    flex-direction: column;
    width: 50%;

    .forum-plate-wrapper {
      border-right: 3px solid black;
      display: flex;
      gap: 71px;
      flex-direction: column;
      width: 100%;
      overflow: auto;
      height: 413px;
      &::-webkit-scrollbar {
        display: none;
        overflow: hidden;
      }
    }
  }
  .featured-tournament {
    display: flex;
    flex-direction: column;
    width: 50%;
    .banner-frame-wrapper {
      display: flex;
      gap: 74px;
      flex-direction: column;
      height: 413px;
      width: 100%;
      overflow: auto;

      &::-webkit-scrollbar {
        display: none;
      }

      .banner-text {
        @include font-weight(bold);
        font-family: $archivo;
        margin-top: 20px;
        margin-left: 10px;
      }
    }
  }
}
</style>
