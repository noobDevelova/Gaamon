<template>
  <div class="profile-menu">
    <div class="profile-set-dropdown">
      <slot name="profile-user">
        <button
          class="component-button"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          <img
            class="user-img-profile"
            src="../../assets/img/user_profile_img.svg"
            alt=""
          />
        </button>
        <ul class="dropdown-menu dropdown-menu-end">
          <li class="dropdown-list">
            <router-link to="/my-profile" class="dropdown-item">
              <span class="material-symbols-outlined"> person </span>
              My Profile
            </router-link>
          </li>
          <li class="dropdown-list">
            <router-link to="/my-profile" class="dropdown-item">
              <span class="material-symbols-outlined"> group </span>
              My Group
            </router-link>
          </li>
          <li class="dropdown-list">
            <a class="dropdown-item" href="#">
              <span class="material-symbols-outlined"> bookmark </span>
              Saved
            </a>
          </li>
          <li class="dropdown-list">
            <a class="dropdown-item" href="#">
              <span class="material-symbols-outlined"> credit_card </span>
              Payment Method
            </a>
          </li>
          <li class="dropdown-list">
            <a class="dropdown-item" href="#">
              <span class="material-symbols-rounded"> settings </span>
              Setting
            </a>
          </li>
          <li class="dropdown-list">
            <a class="dropdown-item" href="#">
              <img src="../../assets/img/purchase_history.svg" alt="" />
              Purchase History
            </a>
          </li>
          <li class="dropdown-list">
            <a class="dropdown-item" href="#">
              <span class="material-symbols-rounded"> logout </span>
              Log Out
            </a>
          </li>
        </ul>
        <!-- @click="$store.dispatch('logout')" -->
      </slot>
    </div>
    <div class="notification-dropdown">
      <slot name="notification">
        <button
          class="component-button"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          <span class="material-symbols-rounded"> notifications </span>
        </button>
        <ul class="dropdown-menu">
          <li class="dropdown-list">
            <a href="" class="dropdown-item">
              <div class="notif-item">
                <img
                  class="user-notif-profile"
                  src="../../assets/img/notif_img.svg"
                  alt=""
                />
                <p class="notif-description">
                  Germo <span class="context">Has following you</span><br />
                  <span class="time-description">4 Hours ago</span>
                </p>
              </div>
            </a>
          </li>
          <li class="dropdown-list">
            <a href="" class="dropdown-item">
              <div class="notif-item">
                <img
                  class="user-notif-profile"
                  src="../../assets/img/notif_img.svg"
                  alt=""
                />
                <p class="notif-description">
                  Germo <span class="context">Has following you</span><br />
                  <span class="time-description">4 Hours ago</span>
                </p>
              </div>
            </a>
          </li>
          <li class="dropdown-list">
            <a href="" class="dropdown-item">
              <div class="notif-item">
                <img
                  class="user-notif-profile"
                  src="../../assets/img/notif_img.svg"
                  alt=""
                />
                <p class="notif-description">
                  Germo <span class="context">Has following you</span><br />
                  <span class="time-description">4 Hours ago</span>
                </p>
              </div>
            </a>
          </li>
          <li class="dropdown-list">
            <a href="" class="dropdown-item">
              <div class="notif-item">
                <img
                  class="user-notif-profile"
                  src="../../assets/img/notif_img.svg"
                  alt=""
                />
                <p class="notif-description">
                  Germo <span class="context">Has following you</span><br />
                  <span class="time-description">4 Hours ago</span>
                </p>
              </div>
            </a>
          </li>
          <li class="dropdown-list">
            <a href="" class="dropdown-item">
              <div class="notif-item">
                <img
                  class="user-notif-profile"
                  src="../../assets/img/notif_img.svg"
                  alt=""
                />
                <p class="notif-description">
                  Germo <span class="context">Has following you</span><br />
                  <span class="time-description">4 Hours ago</span>
                </p>
              </div>
            </a>
          </li>
        </ul>
      </slot>
    </div>
    <div class="chat-list-dropdown">
      <slot name="chat">
        <button
          class="component-button"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          <img src="../../assets/img/chat_icon.svg" alt="" />
        </button>
      </slot>
    </div>
    <div class="mvp-menu-dropdown">
      <slot name="mvp-user">
        <button
          class="component-button"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          <span class="material-symbols-rounded"> menu </span>
        </button>
      </slot>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";

.profile-menu {
  position: absolute;
  display: flex;
  flex-direction: row-reverse;
  gap: 1rem;
  right: 0;
  .component-button {
    position: relative;
    @extend .btn-master;
    width: 2.5rem;
    height: 2.5rem;
    text-align: center;

    span {
      display: flex;
      align-items: center;
    }

    .user-img-profile {
      position: absolute;
      top: 0px;
      left: 0px;
      max-width: 2.25rem;
      max-height: 2.25rem;
    }
  }
  .profile-set-dropdown {
    .dropdown-menu {
      z-index: 392898094893084;
      width: 14rem;
      // margin-top: 0.89rem;
      border-top-left-radius: 0px;
      border-top-right-radius: 0px;
      border-bottom-left-radius: 20px;
      border-bottom-right-radius: 20px;
      border-inline: 2px solid black;
      border-bottom: 2px solid black;
      background-color: $kuningSummer;
      transform: translateX(10px);
      .dropdown-list {
        padding: 0.5rem;

        .dropdown-item {
          display: flex;
          gap: 8px;
          align-items: center;
          @include font-weight(semibold);
          width: 100%;
          height: 2.5rem;
          margin-inline: auto;
          transition: all 0.2s ease-out;
          border: 1px solid $kuningSummer;
          &:hover {
            transition: all 0.2s ease-in;
            border: 1px solid black;
            background-color: $kuningSummer;
            box-shadow: 2px 2px 0px #000000;
          }
        }
      }
    }
  }

  .notification-dropdown {
    .dropdown-menu {
      width: 17rem;
      // margin-top: 0.89rem;
      border-top-left-radius: 0px;
      border-top-right-radius: 0px;
      border-bottom-left-radius: 20px;
      border-bottom-right-radius: 20px;
      border-inline: 2px solid black;
      border-bottom: 2px solid black;
      background-color: $kuningSummer;
      transform: translateX(-30px);
      .dropdown-list {
        padding-top: 0.2rem;
        padding-inline: 0.5rem;
        .dropdown-item {
          display: flex;
          gap: 8px;
          align-items: center;
          justify-content: center;
          @include font-weight(semibold);
          width: 100%;
          height: 4rem;
          margin-inline: auto;
          transition: all 0.2s ease-out;
          border: 2px solid $kuningSummer;
          // border: 2px solid black;
          &:hover {
            border: 2px solid black;
            transition: all 0.2s ease-in;
            border-radius: 5px;
            background-color: $kuningSummer;
            box-shadow: 2px 2px 0px #000000;
          }
          .notif-item {
            display: flex;
            flex-direction: row;
            gap: 10px;
            align-content: center;
            .notif-description {
              @include font-weight(semibold);
              font-size: 12px;
              margin-bottom: 0;
              .context {
                color: $blurGrey;
                display: inline-block;
              }
              .time-description {
                @include font-weight(bold);
                font-size: 10px;
              }
            }
          }
        }
      }
    }
  }
}
</style>
